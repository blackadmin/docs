## Particle Documentation [![Build Status](https://travis-ci.org/spark/docs.svg?branch=feature/server-side-rendering)](https://travis-ci.org/spark/docs)
=======

Here you'll find the documentation for the Particle platform, including the Particle Cloud, Photon, and Spark Core.

To view this documentation, visit [our website](http://docs.particle.io), where the documentation is hosted.

**Note**: This is a new public repository as of May 18, 2015. All
outsdanding pull requests from the old docs repository have been closed.
Please re-open them in this repo.

### Installation

To host this documentation locally, you'll need Node.js and npm:

    brew install nodejs

If you don't already have Grunt installed, you'll need that too:

    npm install -g grunt-cli

Once you have the dependencies, navigate to this repository's directory on your machine, and then:

    npm install

to install any other necessary dependencies:

### Hosting locally

This documentation uses Grunt and Assemble to build and push documentation updates. Once everything's installed, to build the documentation, type:

`grunt build`

The documentation will be located in the `build` directory. If you would like to host this documentation locally, try:

`grunt server`

This will set up a Connect server and load the local documentation in a web browser. If you make changes, the browser should automatically refresh.

### Deployment

When updated documentation is pushed to the master branch, it is automatically pushed to Amazon S3 by Travis CI.

Travis calls `grunt deploy`, which is the same as `grunt build`, except that it also zips up the docs for downloading.

To see the latest build, visit the [Travis CI page](https://travis-ci.org/spark/docs).

### Organization

The majority of the content herein is stored in the `src/content/en` directory as a set of Markdown files. Assets such as images and javascript are stored in the `src/assets` directory.

Within the `en` subdirectory, there are three subfolders: `core`,
`photon`, and `shared`. Files in `core` will only be shown in the menu when the user
is viewing Core-specific docs, and `photon` files will be visible when
viewing Photon-specific docs. Files in `shared` will be nested under both
devices, so put pages here that apply to both the Core and the Photon.

If you create a new file under the `shared`, please add `shared: true`
to the front-matter at the beginning of the MD file so that the link to
edit the file on GitHub will be correct. For instance:

```
---
word: API
title: Cloud code (API)
order: 4
shared: true
---
```

### Attributions

Some of this documentation is derived from the [Arduino documentation](http://arduino.cc/en/Reference), as the Arduino/Wiring language and libraries are used extensively on the Spark Core.

This documentation was originally built using [Flatdoc](http://ricostacruz.com/flatdoc/), an awesome tool for building beautiful documentation from simple Markdown files. We have made many modifications since, but the inspiration remains.

### Contributions

This documentation is managed by Particle, but supported by the community. We welcome contributions such as:

* Edits to improve grammar or fix typos
* Edits to improve clarity
* Additional annotated examples for others to follow
* Additional content that would help provide a complete understanding of the Particle platform
* Translations to other languages

Making a contribution is as simple as forking this repository, making edits to your fork, and contributing those edits as a pull request. For more information on how to make a pull request, see [Github's documentation](https://help.github.com/articles/using-pull-requests/).

### License

These files have been made available online through a [Creative Commons Attribution-ShareAlike 3.0 license](http://creativecommons.org/licenses/by-sa/3.0/us/).

You are welcome to distribute, remix, and use these files for commercial purposes. If you do so, please attribute the original design to Spark Labs, Inc. both on the website and on the physical packaging of the product or in the instruction manual. All derivative works must be published under the same or a similar license.
