# Introduction

This example shows how to use pattern lab using only tooling installed
in the build containers.

This assumes that the pattern-lab-starter directory is a sibling to the
current directory. If you want to adjust this, change the volume mapping
in base.yml.

# Usage

* Clone [pattern-lab-starter](https://github.com/phase2/pattern-lab-starter)
as a sibling to this directory. Example `git clone git@github.com:phase2/pattern-lab-starter.git ../pattern-lab-starter`
* Prepare pattern lab: `docker-compose -f install.yml run --rm install`
* Starting server and file processing: `docker-compose up`. You can view
the pattern lab instance at [http://www.pl.vm:3050](http://www.pl.vm:3050)
once file processing has completed and the server has started. Watch
the output of the container to see the start message though note that
the URLs do not all report incorrectly in that message.
* Speed up change propogation to container by running `devtools watch ../pattern-lab-starter/source`
* If you want to use tools interactively, you can use the cli container
by running `docker-compose -f cli.yml run --rm cli`

# File Descriptions

## base.yml

Base setup for other files to inherit services from.

## docker-compose.yml

Defines a server instance that hosts the pattern lab files and watches
for file changes that need processing.

## .devtools-watch-ignore

Exclude patterns for `devtools watch` command. Examples are for Vim and
PhpStorm.

## install.yml

Container for doing the initial pattern lab starter installation.

## cli.yml

Container for command line within build container for interactive use
of pattern lab commands and build tools.
