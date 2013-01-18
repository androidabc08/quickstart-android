Android Quickstart
==================

A template project which will help you get started with Android
development. It collects years of knowledge, tools and scripts to aid you
with new projects.

It assumes that all developers use Eclipse or the ADT Bundle during
development while Ant is used only for automated builds/CI. Consequences of
this choice include inability to automate coding style checks, automate
formatting of source code (which is done by Eclipse each time a file is
saved anyways) and inability to use other IDEs (if consistency is of
paramount importance). The rationale is that this simplifies the skeleton
project: instead of trying to support all possible workflows we simply
assume that code is written in Eclipse and integration is done by Ant.

Developed and tested on Ubuntu 12.04.1. It should work on all POSIX
compatible environments provided that required dependencies are installed.


## What's Inside

* Project Management
  * Apache Ivy to resolve/download JAR dependencies
  * Python script to reference popular 3rd party Android libraries (which
    cannot be distributed as simple JAR files, thus cannot be downloaded by
    Ivy) libraries as git submodules and Android library dependencies.
  * Python script to hardlink Google libraries (Cloud Messaging, Maps API,
    etc) from the SDK directory to the project `libs/` directory.

* Compatibility:
  * Minimum platform version: `android-15` (Android 4.0.3)
  * Target platform version: `android-17` (Android 4.2.0)

* Coding style, static analysis:
  * Checkstyle
  * FindBugs

* Boilerplate code/Output size reduction:
  * Android Annotations
  * ProGuard enabled by default

* VCS/IDE support:
  * Script to install Checkstyle and FindBugs plugins into an existing
    Eclipse installation


## Dependencies

This stuff must be already installed on your system:

* ADT Bundle with SDK Tools >= 21;
* Apache Ant >= 1.8.0;
* Apache Ivy >= 2.2.0-rc1;
* Git >= 1.7.9;
* OpenJDK 6;


## Setup

Run these commands in a terminal:

    # Clone the repository into its own 'quickstart' branch
    git clone -o quickstart git://github.com/lvillani/quickstart-android
    cd quickstart-android

    # Branch off from 'quickstart' into 'master'
    git branch master
    git checkout master

    # Re-generate local.properties
    android update project -p .

    # Resolve dependencies
    ant resolve


### Eclipse

This repository comes with a pre-configured Eclipse project. To use it click
`File` -> `Import` -> `General` -> `Existing Projects into Workspace` and
select the root directory of the repository you have just cloned.


## Additional Resources

* __Android Kickstarter__: <http://androidkickstartr.com/>
* __Android Views__: <http://www.androidviews.net/>
* __Asset Studio__: <http://android-ui-utils.googlecode.com/hg/asset-studio/dist/index.html>


## FAQ

__Q:__ Why don't you support IntelliJ, Maven, Emacs, Vi, Vim, ...?

__A:__ Google and AOSP declared Eclipse as the offically supported IDE and
Ant as the officially supported build tool. Sure, Eclipse is slow, bloated
and gets mad from time to time and Ant is not as elegant as Maven but
that's what comes in the box (Fun anecdote: we actually switched back from
NetBeans/Maven to Eclipse/Ant because the alternatives were even worse than
what was officially supported). Supporting official tools has the absolute
priority over everything else.


## License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute
this software, either in source code form or as a compiled binary, for any
purpose, commercial or non-commercial, and by any means.

In jurisdictions that recognize copyright laws, the author or authors of this
software dedicate any and all copyright interest in the software to the public
domain. We make this dedication for the benefit of the public at large and to
the detriment of our heirs and successors. We intend this dedication to be an
overt act of relinquishment in perpetuity of all present and future rights to
this software under copyright law.

Unless you really want to, do not even mention that the copied content
originates from this skeleton library. Its sole purpose is to be copied into
other projects.

The above statements apply to all content in this skeleton library, even when
the COPYING files, or the headers in the files state otherwise, they are just
common examples.
