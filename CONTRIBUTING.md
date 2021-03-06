# How to contribute to Wordseer

If you'd like to contribute, we'll be happy to have your help. 

First and foremost, feel free to get in touch! The WordSeer project is directed by [Prof. Marti Hearst](http://people.ischool.berkeley.edu/~hearst/) 
at the University of California, Berkeley, School of Information; you may contact her via email 
at hearst@berkeley.edu.

We welcome both technical and non-technical contributions to the WordSeer project. Sure, 
there are software bugs to be fixed (and [plenty of them](https://github.com/Wordseer/wordseer/issues)),
but there are also features to be designed and user studies to be done. 

WordSeer began with Aditi Muralidharan's PhD research and engineering at UC Berkeley with Prof. Hearst; 
there is a wealth of information on that research available on [the WordSeer website](http://wordseer.berkeley.edu/publications-2/)
that can provide useful background for both technical and non-technical contributors.

If you're looking to dive in and start coding, here's an overview of our development process.

## Branching

We have two main branches:

- `master`, for stable, production-ready code
- `development`, for recent and unstable code

Feature branches that wish to make a change to the application should be
branched from `development`. Once they are ready, they'll be merged into
`development`, which is periodically merged into `master` once it is stable.

Hotfixes that should be applied quickly to `master` are branched off of `master`
and called `hotfix-xyz`. Unit tests must be passing in a hotfix branch before
it can be merged.

Unit tests must always be passing in `master`.

## Ways to contribute

1. [Report bugs](https://github.com/Wordseer/wordseer/issues/new)

2. Fix bugs - we have a conveniently organized
[system](https://waffle.io/Wordseer/wordseer) for contributors to see
what's ready to be [worked on](https://github.com/Wordseer/wordseer/issues?q=is%3Aopen+is%3Aissue+label%3Aready).
Once you've fixed something, you can create a pull request.

## Documentation
Documentation is
[available on readthedocs](http://wordseer.readthedocs.org). You can also
build it yourself:

	cd docs/
	make html

Or, on windows, simply run `make.bat` in the same directory.

## Testing
Simply run `runtests.py`:

    python runtests.py

## Version history

Up through versions 3.X, Wordseer was a collection of PHP/MySQL and JavaScript 
applications. This repository initiates version 4, which is a reimplementation of WordSeer's
PHP components in Python/SQLite that can be run on local machines without requiring
a web server setup. There are two primary components to this new codebase:

1. A rewrite of the
[original implementation](https://bitbucket.org/silverasm/wordseer/overview)
of wordseer into python from PHP.

    This is located in `app/wordseer/`. It is the server-side and web interface
    code for the WordSeer application, written in Python using the Flask
    framework and several web framework libraries.


2. An implementation of
[wordseerbackend](https://bitbucket.org/silverasm/wordseerbackend/overview) in
more maintainable python.

    This is located in `app/preprocessor/`. It is the pipeline or
    preprocessing code for uploaded data sets.
