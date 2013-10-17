Heroku buildpack: Python/Node
===============================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for Python apps with added support for Node package dependencies.

It uses:

* [pip](http://www.pip-installer.org/)
* [npm](https://npmjs.org/)

Installation
------------

Use [heroku-buildpacks](https://github.com/heroku/heroku-buildpacks):

``` bash
$ heroku config:set BUILDPACK_URL=https://github.com/sgtFloyd/heroku-buildpack-python-node
```

Usage
-----

The buildpack will detect your app as Python if it has the file `requirements.txt` in the root. 

It will use Pip to install your dependencies, vendoring a copy of the Python runtime into your slug.

### Node Dependencies

If your project contains a `package.json`, npm will be used install Node dependencies.

### Specify a Runtime

You can also provide arbitrary releases Python with a `runtime.txt` file.

``` bash
$ cat runtime.txt
python-3.3.0
```
