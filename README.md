## git-shallow-clone-orb
[![CircleCI](https://circleci.com/gh/hellodigit/git-shallow-clone-orb.svg?style=svg)](https://circleci.com/gh/hellodigit/git-shallow-clone-orb) [![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/hellodigit/git-shallow-clone)](https://circleci.com/orbs/registry/orb/hellodigit/git-shallow-clone)

## Usage

See the [orb registry listing](http://circleci.com/orbs/registry/orb/hellodigit/git-shallow-clone) for usage guidelines.

## Contributing

We welcome [issues](https://github.com/hellodigit/git-shallow-clone-orb/issues) to and [pull requests](https://github.com/hellodigit/git-shallow-clone-orb/pulls) against this repository!

## MEMO

* normal push without specific pattern of a tag, dev build will run.
* push tag for production release.
    * master-major.v1.0.0
    * master-minor.v1.1.0
    * master-patch.v1.1.1

> NOTE: `orb-tools/dev-promote-prod` cleanup-tags is set to true to remove `master.*` tags on publish orb to the production.

## Basic orb setup

setup orb account and namespace.

```shell
# require perconal api tokens
$ circleci setup
$ circleci namespace create hellodigit github hellodigit
$ circleci orb create hellodigit/git-shallow-clone
```

validate before publish.

```
$ cd ./src
$ circleci orb validate orb.yml
```

publish orb to the alpha.

```
$ cd ./src
$ circleci orb publish orb.yml hellodigit/git-shallow-clone@dev:alpha
```


publish orb to the dev.

```
$ cd ./src
$ circleci orb publish orb.yml hellodigit/git-shallow-clone@dev:0.x.0
```

publish orb to the production.

```
$ cd ./src
$ circleci orb publish promote hellodigit/git-shallow-clone@0.x.0
```
