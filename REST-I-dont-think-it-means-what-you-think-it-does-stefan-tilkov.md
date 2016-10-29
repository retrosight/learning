#GOTO 2014 • REST: I don't Think it Means What You Think it Does

by Stefan Tilkov

https://www.youtube.com/watch?v=pspy1H6A3FM

This is a summary of the slides used by Stefan Tilkov in his excellent talk on REST.

## Identification of resources

* Universal identity
* URIs
* Link targets
* Bookmarks
* Entry points

"Everything of value should have its own URI so you can reference it and can access it directly."

"Give everything important its own URI."

## Resource manipulation through representations.

* Separation of concerns
  * Data
  * Identity
  * Location
* Multiple representations
* Metadata
* Reduced dependency
* Processing model

## Hypermedia as the engine of application state (HATEOAS)

* Links
* Connections
* Forms
* Flow
* Status

## Self descriptive messages

* Standardization
* Metadata
* Provider independence
* Intermediaries
  * Caching

## What's in the Web?

* Lots of things with URLs
* Connected with Hypermedia
* Governed by standard formats

## Common misconceptions

### REST is about nice URIs <-- IT IS NOT

What makes a URI 'RESTful'?

```
http://example.com/customers/format?drive=c
http://example.com/customers/getDetails?id=13
http://example.com/customers/delete?id=13
http://example.com/customers/13
http://example.com/customers/13/edit
^^^  REST is about nice URIs < IT'S NOT  ^^^
```

"You can make no assumption whatsoever about the characters that make up a URI."

"There is no such thing as a 'RESTful URI'."

```
------------------------------------------------------------------------
|  |--------|-----|-------------|-------------------|---|-----------|  |
|  | http   | :// | example.com | /customers/delete | ? | id=13     |  |
|  |        |     |             |                   |   |           |  |
|  | scheme |     | authority   | path              |   | parameter |  |
|  |--------|-----|-------------|-------------------|---|-----------|  |
|                                                                      |
|                            opaque URI                                |
------------------------------------------------------------------------
```

You should not care about URIs -- the hypermedia context is the important piece.

```text
{
  "customer": {
      |   "name": "John Doe",
      |   "orders": "http://----------"
  }   |      ^
}     |      |
      |      |
     Hypermedia context
```

* It is fine for the server to decompose the URI to dispatch things to code.
* If the client code is concatenating strings to build URIs something is wrong because you have not applied the hypermedia aspect.

### REST = URI patterns + GET, PUT, POST, DELETE <-- CLOSE, BUT NO

URI | Method | Meaning
----|--------|--------
http://example.com/v1/customers|POST|Create new customer
http://example.com/v1/customers/{id}|GET|Get customer details
http://example.com/v1/customers{id}/orders|GET|Get list of customer orders

* Documented URIs become APIs
* Assumptions about server details become facts
* Versions in URIs cause change for no good reason

## What are you 'versioning'?

@27:50

```
Data          <-- Yes
Documentation <-- Yes
Formats       <-- Yes
APIs          <-- No
```

### Versioning guidelines

* Use different media types for different things
* Use version numbers in URIs to version the resource itself
* Create new resources for new aspects
* Reserve space for links
* Version your docs

Wait, what?

Yes, no versioning.


## Postel's Law

```
TCP implementations should follow a general principle of robustness:
be conservative in what you do, be liberal in what you accept from
others. ~ https://tools.ietf.org/html/rfc761
```

```
Strict, Critical, Draconian (Output)
             |            |
             V            V
      |-----|      |-----|
----->|     |----->|     |
      |-----|      |-----|
     ^            ^
     |            |
Liberal, Loose, Tolerant (Input)
```

* Be kind to each other.

## Client and Server Rules

Client | Server
-------|-------
Don't depend on URI structure|Don't break URI structure unnecessarily
Support unknown links|Evolve via additional resources
Ignore unknown content|Support older formats

## How to hypermedia-enable your service interfaces

### Step 1: Service Document

* The home page for the API.
* https://mnot.github.io/I-D/json-home/

### Step 2: Resource links

`GET /order/123`

```json
{
  "order": {
    "date": "2017-07-02",
    "total": "1240.02",
    "links": [
      { "rel": "self", "href": "http://example.com/orders/123" },
      { "rel": "contacts", "href": "http://example.org/A3BEF1" }
    ]
  }
}
```

### Step 3: State Transition Links

```
                                                                      -------------
            update          cancel                                    |           |
           -----------|   |-----------------------------------------> | cancelled | --------------|
           |          |   |                                           |           |               |
           |          |   |                                           -------------               |
           |          |   |                                                                       |
           |      -------------             -------------             -------------               |
           V      |           |  acccept    |           |  ship       |           |               V
start ----------> | received  | ----------> | accepted  | ----------> | fulfilled | ---------> completed
                  |           |             |           |             |           |               ^
                  -------------             -------------             -------------               |
                          |                                                                       |
                          |                 -------------                                         |
                          |                 |           |                                         |
                          |---------------> | rejected  |-----------------------------------------|
                            reject          |           |
                                            -------------
```

```json
{
  "order": {
    "state": "received",
    "links": [
      { "rel": "cancel", "href": "http://..." },
      { "rel": "accept", "href": "http://..." },
      { "rel": "reject", "href": "http://..." }
    ]
  }
}
```

### Hypermedia APIs = Responses with Links <-- NOT ONLY

Rule #1; Don't have clients build URIs using string concatenation

Provide recipes

```html
<form action='http://example.com/search' method='GET'>
  Search for: <input type='text' name='query'>
              <input type='submit'
</form>
```
```json
{
  "rel": "search",
  "template": "http://example.com/search?q={query}"
}
```

```html
<form action='http://example.com/add' method='POST'>
  First:    <input type='text' name='first'>
  Last:     <input type='text' name='last'>
  Birthday: <input type='text' name='bdate'>
            <input type='submit'
</form>
```
```json
{
  "target": "http://example.com/add",
  "rel": "add",
  "template": {
    "first": "...",
    "last": "...",
    "bdate": "..."
  }
}
```

### REST = A different approach to service interfaces <-- TOO SIMPLE

#### Point-to-point integration

```
-------------                  -------------
|           |       -----      |           |
| System B  | ----->|   |----> | System A  |
|           |       -----      |           |
-------------                  -------------
```

#### Service interfaces

```
-------------
|           |
| Client 1  | --------|
|           |         |
-------------         |
-------------         |        -------------
|           |       -----      |           |
| Client 2  | ----->|   |----> | Server    |
|           |       -----      |           |
-------------         |        -------------
-------------         |
|           |         |
| Client n  | --------|
|           |
-------------
```

#### Hypermedia types

```
-------------             -------------            -------------
|           | ------------|           |----------> |           |
| Client 1  |             |           |            | Server A  |
|           | ------|     |           |            |           |
-------------       |     |           |            -------------
-------------       |     |           |            -------------
|           |       ------|           |----------> |           |
| Client 2  | ------------|  Format   |----------> | Server B  |
|           |       ------|           |----------> |           |
-------------       |     |           |            -------------
-------------       |     |           |            -------------
|           | ------|     |           |            |           |
| Client n  |             |           |            | Server n  |
|           | ------------|           |----------> |           |
-------------             -------------            -------------
```

Examples

* `application/atom+xml`
* `application/opensearchdescription+xml`
* `application/vnd.collection+json`
* `application/hal+json`
* `application/vnd.siren+json`
* `text/html`

#### Benefits of Using HTML as Your Hypermedia Format

* Ubiquity
* Well-known, well supported hypermedia controls
* A pretty good standard client
* Lots of programming tools
* UIs as a side-effect
