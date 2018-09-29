I'd like to invite you to join me working towards a more inclusive environment working in source code repositories residing in GitHub.

The following steps will:

* Remove the terminology `master` from the repository.
  * I will note it will not _completely_ remove the terminology from the GitHub interface -- but for most users (who can't see or edit Settings) it greatly reduces it's presence.
* Add the Contributor Covenant from https://www.contributor-covenant.org/.

I have done this for all of my repositories, both public and private, and hope you will as well.

C-

## Create the new default / main branch

I have decided on `primary` as my default / main branch -- feel free to choose your own name which is more neutral or inclusive.

If you already use another branch as the default / main branch you can skip to the next step.

In the command line, starting in the `master` branch:

```shell
git checkout -b "primary"
git push origin primary
git branch --set-upstream-to=origin/primary primary
```

## Set the default main branch

* Go through all of the steps here to set the default branch to the new branch created above: https://help.github.com/articles/setting-the-default-branch/
* Click the Update button.
* Click the "I understand, update the default branch." button.

## Change the branch used for GitHub Pages to gh-pages

> Note: After this step you will now have to merge your new branch to `gh-pages` to update the website generated via this feature.

* Go through all of the steps here: https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/#enabling-github-pages-to-publish-your-site-from-master-or-gh-pages
* Choose the option for `gh-pages`.

## Delete the old branch in GitHub

* Go through all of the steps here to delete the old branch: https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/#deleting-a-branch

## Delete the old branch in local

In the command line:

```shell
git branch -D master
```

## Add the contributor covenant

In the command line:

```shell
npm install -g covgen
covgen {your_email_address}
```

* For subsequent projects, simply repeat the second command.
* This will create `CODE_OF_CONDUCT.md` in the root of the repository which I rename `code-of-conduct.md`.
* I modify the markdown (line 58) to include a `mailto:` hyperlink for my email address to make it a little more user friendly: [name@example.com](mailto:name@example.com)

## Add language to readme.md to point to the contributor covenant

I have extended the wording suggested on the Contributor Covenant website to point back to that website:

```
Please note that this project is released with a [Contributor Code of Conduct](./code-of-conduct.md). By participating in this project you agree to abide by its terms. Learn more at [https://www.contributor-covenant.org/](https://www.contributor-covenant.org/).
```

## Push / merge to the new branch.

```shell
git add .
git commit
  {Spend weeks trying to exit VIM} <-- HAHAHAHA {clears throat}
git push origin primary
```

...or whatever pull / merge process you'd like to follow.

All done and thank you. ;)
