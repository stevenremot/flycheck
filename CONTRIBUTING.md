# Contribution guidelines #

Thank you very much for your interest in contributing to Flycheck!  We’d like to
warmly welcome you in the Flycheck community, and hope that you enjoy your time
with us!

There are many ways to contribute to Flycheck, and we appreciate all of them.
We hope that this document helps you to contribute.  If you have questions,
please ask on our [issue tracker][] or in our [Gitter chatroom][gitter].

Please note that all contributors are expected to follow our
[Code of Conduct][coc].

[issue tracker]: https://github.com/flycheck/flycheck/issues
[gitter]: https://gitter.im/flycheck/flycheck
[coc]: http://www.flycheck.org/conduct.html

## Bug reports ##

Bugs are a sad reality in software, but we strive to have as few as possible in
Flycheck.  Please liberally report any bugs you find.  If you are not sure
whether something is a bug or not, please report anyway.

If you have the chance and time please [search existing issues][issues], as it’s
possible that someone else already reported your issue.  Of course, this doesn’t
always work, and sometimes it’s very hard to know what to search for, so this is
absolutely optional.  We definitely don’t mind duplicates, please report
liberally.

To open an issue simply fill out the [issue form][].  To help us fix the issue,
include as much information as possible.  In doubt, better include too much than
too little.  Here’s a list of facts that are important:

* What you did, and what you expected to happen instead
* Your Flycheck setup from `M-x flycheck-verify-setup`
* Your operating system
* Your Emacs version from `M-x emacs-version`
* Your Flycheck version from `M-x flycheck-version`

[issues]: https://github.com/flycheck/flycheck/issues?utf8=✓&q=is%3Aissue
[issue form]: https://github.com/flycheck/flycheck/issues/new

## Feature requests ##

TODO

## Pull requests ##

Pull Requests are the primary mechanism to submit your own changes to Flycheck.
Github provides [great documentation][pull-requests] about Pull Requests.

Please make your pull requests against the `master` branch.

TODO: How to test!

All pull requests are reviewed by a [maintainer][maintainers].  Feel free to
mention individual developers (e.g. @lunaryorn) to request a review from a
specific person, or @flycheck/maintainers if you have general questions or if
your pull request was waiting for review too long.

Additionally, all pull requests go through automated tests on
[Travis CI][travis-prs] which check code style, run unit tests, etc.  After the
pull request was reviewed and if all tests passed a maintainer will eventually
cherry-pick or merge your changes and close the pull request.

[pull-requests]: https://help.github.com/articles/using-pull-requests/
[travis-prs]: https://travis-ci.org/flycheck/flycheck/pull_requests
[maintainers]: http://www.flycheck.org/people.html#maintainers
[Rake]: http://docs.seattlerb.org/rake/
[bundler]: http://bundler.io/

### Commit guidelines ###

## Writing documentation ##

## Out of tree contributions ##

## Issue management ##

----

## Contributing code ##

Contributions of code, either as pull requests or as patches, are *very*
welcome, but please respect the following guidelines.

### General ###

* Write good and *complete* code.
* Provide use cases and rationale for new features.

### Code style ###

* Generally, use the same coding style and spacing.
* Do not use tabs for indentation.
* Add docstrings for every declaration.
* Make sure your code compiles without warnings with `rake compile`, and has no
  checkdoc issues with `M-x checkdoc-buffer` or `C-c ? d`.  If you are using
  Flycheck, just make sure that your code has no Flycheck warnings.

### Commit messages ###

Write commit messages according to [Tim Pope's guidelines][]. In short:

* Start with a capitalized, short (50 characters or less) summary, followed by a
  blank line.
* If necessary, add one or more paragraphs with details, wrapped at 72
  characters.
* Use present tense and write in the imperative: “Fix bug”, not “fixed bug” or
  “fixes bug”.
* Separate paragraphs by blank lines.
* Do *not* use special markup (e.g. Markdown).  Commit messages are plain text.
  You may use `*emphasis*` or `_underline_` though, following conventions
  established on mailing lists.

This is a model commit message:

    Capitalized, short (50 chars or less) summary

    More detailed explanatory text, if necessary.  Wrap it to about 72
    characters or so.  In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body.  The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together.

    Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
    or "Fixes bug."  This convention matches up with commit messages generated
    by commands like git merge and git revert.

    Further paragraphs come after blank lines.

    - Bullet points are okay, too

    - Typically a hyphen or asterisk is used for the bullet, followed by a
      single space, with blank lines in between, but conventions vary here

    - Use a hanging indent

[Git Commit][] and [Magit][] provide Emacs mode for Git commit messages, which
helps you to comply to these guidelines.

[Tim Pope's guidelines]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[Git Commit]: https://github.com/magit/magit/
[Magit]: https://github.com/magit/magit/

### Contributing syntax checkers ###

For syntax checkers, some special guidelines apply in addition to the above:

* Provide a link to the website of the syntax checker tool in the comments of
  your pull request.
* Add a proper docstring to your syntax checker, including this URL.
* Add unit tests for your syntax checker, or provide example code that triggers
  errors for each error pattern of the syntax checker.
* Make sure that your new syntax checker passes all required tests, with
  `test/run.el (new-checker-for LANGUAGE)`, where `LANGUAGE` is the programming
  language the checker is for.
* Ideally, extend the [Flycheck testing VM][] with recipes to install the new
  syntax checker.

Unit tests that can run on Travis CI are **mandatory** for all syntax checkers
in Flycheck.

[Flycheck testing VM]: https://github.com/flycheck/flycheck-vm

### Pull requests ###

* Use a **topic branch** to easily amend a pull request later, if necessary.
* Do **not** open new pull requests, when asked to improve your patch.  Instead,
  amend your commits with `git rebase -i`, and then update the pull request with
  `git push --force`
* Open a [pull request][] that relates to but one subject with a clear title and
  description in grammatically correct, complete sentences.

Pull requests **must** pass all tests on Travis CI before being merged.

[pull request]: https://help.github.com/articles/using-pull-requests
