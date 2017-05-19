Excerpted from [Spec-ulation Keynote - Rich Hickey](https://www.youtube.com/watch?v=oyLBGkS5ICk)

## Growing Your Software

* Accretion
 * provide more
* Relaxation
 * require less
* Fixation
 * bash bugs

## Breaking Your Software

* Require more
* Provide less
* Unrelated stuff under same name

## Change Is Not A Thing

* It's one of two things
 * Growth
 * Breakage
* In the small (fns), spec can help us determine which, prevent breaking specs
* As long as we don't try to do something silly like versioning specs!

## "Semantic" Versioning | "Semantics"

* 1.2.changed
 * "you don't care"
* 1.changed.0
 * "you don't care"
* changed.0.0
 * "you're screwed"

Even worse...

* "you might be screwed"
* Considered covering of change at _all_ levels
 * Good luck determining where
* Might just as well change the name
 * Going to v2 isn't helping anybody.
 * "We are now playing a different game called the same name."

## Breaking Changes Are Broken

* Full stop
* Don't do it
* Don't try to figure out the best way to do it
* Avoid breakage by turning it into accretion
 * old and new can co-exist

## So SemVer (Semantic Versioning) is Broken?

* Yes
 * It is, in part, _about_ how to ship breakage.
 * and the other 'semantics' are of little utility
* What instead?
 * Maybe chronological versioning?
  * YYYYMMDD.HHMMSS
  * Conveys more and supports some forms of relativism

## What about Git?

* Wonderful, immutable, truth-of-the-code system, widely adopted
* Content-based addressing
* Almost completely ignored by artifacts/versioning, even though code basis.
* Deserves a role
 * but, SHAs vs order/causality/readability

## What about Web Services?

* Same problems, same mistakes
 * `Versioning` non-answer
 * Conflating collections w/ contents
* Web service is a collection of ops
* ops require/provide
* Accretion could prevent a lot of client / service version hell

## "This is Impossible / Impractical"

* Nope
* Many examples of decade+ compatibility
 * Unix APIs
 * Java
 * HTML
 * Clojure?
* Compatibility a prereqisite of success?

## What is We Never Broke Anything?

* names become enduringly meaningful
* orthogonal compatibility checking becomes possible
* fine grained deps can be explored
* use the latest with impunity
* compose with impunity
