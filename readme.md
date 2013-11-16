Python development
==================

This allows you to build services (Postgres, Redis etc) in a Virtualbox with
minimal effort. Very handy for testing out code.

Prerequisites
-------------

* Linux / Mac / Windows
* [Virtualbox][vbox]
* [Vagrant][vagrant]
* [Git][git]

Setting up
----------

* Open your projects folder in a terminal.
* `git clone git@github.com/simonluijk/python-dev.git`
* `cd python-dev`
* `git submodule update --init`
* `cd chef-repo`
* `git submodule update --init`
* `cd ../`
$ `vagrant up`

Once it has finished download a base image it will setup a Virtualbox image
with Postgresql installed by default. That's all there is to it.

[vbox]: https://www.virtualbox.org/
[vagrant]: http://www.vagrantup.com/
[git]: http://git-scm.com/