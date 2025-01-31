Developing Drools and jBPM
==========================

**If you want to build or contribute to a droolsjbpm project, [read this document](https://github.com/kiegroup/droolsjbpm-build-bootstrap/blob/master/README.md).**

**It will save you and us a lot of time by setting up your development  environment correctly.**
It solves all known pitfalls that can disrupt your development.
It also describes all guidelines, tips and tricks.
If you want your pull requests (or patches) to be merged into master, please respect those guidelines.

# How to build with Awestruct

Follow the instructions of Awestruct's [getting started guide](http://awestruct.org/getting_started/).

First set up your environment correctly, for example on Fedora 24:

$ sudo dnf install ruby
$ ruby --version
ruby 2.2.5p319 (2016-04-26 revision 54774) [x86_64-linux]

$ sudo dnf install rubygem-rake

# This won't immediately work
$ rake setup

# rake setup: Using the bundler fails, this fixes it:
$ sudo dnf install rubygem-bundler

# rake setup: Installing the gem ffi fails, this fixes it:
$ sudo dnf install ruby-devel rpm-build

# rake setup: Installing the gem eventmachine fails, this fixes it:
$ sudo dnf install gcc-c++

# Now it works
$ rake setup

Then build the website (before and after your changes):

    $ rake clean build
    $ firefox _site/index.html

And publish your changes:

    $ rake clean build publish

