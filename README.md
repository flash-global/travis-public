# Travis

## Mindset

The goal of this project is to standardize the usage of 
Travis CI on the Redspher group.

We use the [Travis importation feature](https://docs.travis-ci.com/user/build-config-imports/) to have most flexibility possible.

With this project you can test and deploy easily and you cans extend this standards for specific projects.

## Architecture of the project

On the root directory you can fin all common include not specific for a language.

You can find one directory by language.

Each directory have a common.yml with by default an import to default_tests.yml.

We made that to force tests setup for each languages.


The deployment script made by infra use the CMDB. If you want deploy your application you must configure it. 

## Example of standard PHP library

```
language: php

php:
  - 7.0
  - 7.1
  - 7.2

import:
  - source: flash-global/travis:common.yml@master
    mode: deep_merge_append
  - source: flash-global/travis:php/common.yml@master
    mode: deep_merge_append
```

## Common import file

Check directly the file for more information of the usage.
