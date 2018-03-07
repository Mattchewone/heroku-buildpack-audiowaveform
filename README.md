Heroku buildpack: audiowaveform
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using audiowaveform in your project.  
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Lineage
-------

Shamelessly forked from the [ffmpeg heroku buildpack](https://github.com/shunjikonishi/heroku-buildpack-ffmpeg) by [Shunji Konishi](https://github.com/shunjikonishi).

Usage
-----
To use this buildpack, you should prepare a .buildpacks file that contains this buildpack url and your real buildpack url:

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/lepinsk/heroku-buildpack-audiowaveform

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify that sox is installed by calling:

    $ heroku run "audiowaveform"
