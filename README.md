# DHIL Documentation Guide
This is a guide for creating documentation using [Sphinx](http://www.sphinx-doc.org/en/stable/) for projects supported by the [Digital Humanities Innovation Lab (DHIL)](http://dhil.lib.sfu.ca) at [Simon Fraser University](http://www.sfu.ca).

## Installation
The DHIL documentation guide is built using Sphinx. Sphinx requires [Python 2](https://www.python.org/downloads/) to be installed.

The following are Bash commands. Windows users can use [Cygwin](https://cygwin.com/) or a similar alternative for running them.

### Install Sphinx
```console
$ pip install sphinx
```
### Setup initial Sphinx parameters
```console
$ sphinx-quickstart
```
### Get the code from GitHub
```console
$ git clone https://github.com/sfu-dhil/dhil-docs-guide.git
```
### Build the documentation from source
Inside the dhil-docs-guide directory run: 
```console
$ make html
```
### Open the documentation
```console
$ open build/html/index.html
```
Windows users should try the following:
```console
$ explorer build/html
```
Then click on the index.html in the GUI file explorer that just opened.

