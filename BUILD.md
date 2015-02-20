# Setting up a development environment

The repository contains a `composer.json` file to aid the installation of the necessary development tools.

To set up a development environment, follow these steps:

```sh
#!sh
$ git clone https://github.com/markward/enrol_autoenrol.git
$ cd enrol_autoenrol
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar install
```

## Unit tests

There is a PHPUnit configuration file at `phpunit.xml`. To run the complete test unit test suite, execute:

```sh
#!sh
$ vendor/bin/phing phpunit
```

## Validating coding standards

It is possible to run various static analysis tools against the codebase, checking for (amongst other things) compliance with Moodle
coding standards.

```sh
#!sh
$ vendor/bin/phing quality
```

The raw output will be found in the `logs` directory, whereas an annotated copy of the codebase will be found in the `code-browser`
directory.

## Generating documentation

To generate documentation for the codebase (based upon PHPDocs within the code), execute:

```sh
#!sh
$ vendor/bin/phing api
```

The documentation will be generated in HTML format within the `api` directory.

## Running all of the above

If you want to run test, validate coding standards and generate documentation all in one go, just execute:

```sh
#!sh
$ vendor/bin/phing
```

## Deploying the code

It it possible to deploy the code directly to a Moodle installation by executing:
                                                                                                                                        
```sh
#!sh
$ vendor/bin/phing deploy

Buildfile: build.xml

moodle-enrol_autoenrol > deploy:

Enter your web root for deployment [/var/www/html/] ?  /path/to/moodle/codebase
```
