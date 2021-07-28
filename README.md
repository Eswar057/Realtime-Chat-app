# Realtime-Chat-app
Realtime Chat App using PHP

PHP Project Starter is a command line tool that allows developers to quickly create PHP applications that use common conventions and best-in-breed development tools. The goals of this application are to guide developers towards best practices and get them from zero-to-CI in seconds.

The applications created by this tool have an opinionated directory structure, build system, and pre-configured set of service connections with badges ready to go. Refer to the Tools And Conventions and Directory Structure sections below for more details.

See the examples below for repositories created by the PHP Project Starter tool:

Git Wrapper
HMAC Request Signer
Usage
Install The Command Line Tool
Download Via Browser
Download php-project.phar from https://github.com/cpliakas/php-project-starter/releases/latest,

Download Via Command Line
curl -O http://www.chrispliakas.com/php-project-starter/download/latest/php-project.phar

Test It Out!
Run php php-project.phar --help to see all options supported by the command line tool and ensure that installation succeeded.

It is also common practice to place the php-project.phar file in a location that makes it easier to access, for example /usr/local/bin, and renaming it to php-project. Ensure the file is executable by running chmod 755 so that you don't have to prefix the command with php.

Create A New Project
php php-project.phar new \
  --label="My Project" \
  --description="A longer description for My Project" \
  --namespace="My\Project" \
  cpliakas/my-project
Pass the --jenkins-url option to post a job to Jenkins that consumes the build artifacts.

Make A Repository On GitHub
Make a new repository matching the project name (e.g. cpliakas/my-project) and push your code. Note that the origin remote is already set in the repository.

cd ../path/to/working-copy
git push -u origin master
Configure Other Services
Packagist: Follow the Publish It section
Travis CI: Follow steps one and two of the Getting Started documentation
Scritinizer CI: Follow the Getting Started documentation
Keeping Up-To-Date
Run the following command to update PHP Project Starter to the latest stable version:

php php-project.phar self-update

Using Apache Ant
Running ant in the newly created project's root directory will download Composer, install development dependencies, run PHPUnit, and generate a code coverage report and software metrics in the ./build directory.

The main targets can be found by running ant -p and are listed below:

clean: Cleanup build artifacts
clean-src: Cleanup dependency source code
clean-all: Cleanup build artifacts and dependency source code
composer: Run composer update
lint: Perform syntax check of sourcecode files
pdepend: Calculate software metrics using PHP_Depend
phpcpd: Find duplicate code using PHPCPD
phploc: Measure project size using PHPLOC
phpmd: Perform mess detection using PHPMD, print human readable output.
phpmd-ci: Perform mess detection using PHPMD, creating a log file for the CI server
phpunit: Run unit tests with PHPUnit
Common command line options that set Ant properties are listed below:

-Dcomposer.noselfupdate=1: Do not run composer self-update during the build
-Dcomposer.noupdate=1: Do not run composer update during the build
Tools And Conventions
Tools and conventions that this template expects the PHP project being started to embrace.

Dependency Management
Composer
Build & CI
Apache Ant
Jenkins
PHPUnit
Scrutinizer CI
Travis CI
Code Quality
PHP Analyzer
PHP Coding Standards Fixer
PHP Depend
PHPCPD
PHPLOC
PHPMD
Services
Badge Poser
GitHub
Packagist
Scrutinizer CI
Travis CI
Conventions
EditorConfig
The MIT License (MIT)
PHP Standards Recommendations (PSR)
Template for Jenkins Jobs for PHP Projects
Directory Structure
PHP Project
.
|-- src/
|-- test/
|-- .editorconfig
|-- .gitignore
|-- .scrutinizer.yml
|-- .travis.yml
|-- build.xml
|-- composer.json
|-- phpmd.xml
|-- phpunit.xml
|-- LICENSE
`-- README.md

Build Artifacts
.
`-- build/
    |-- coverage/
    |   `--index.html
    |-- logs/
    |   |-- clover.xml
    |   |-- jdepend.xml
    |   |-- junit.xml
    |   |-- phploc.csv
    |   |-- pmd-cpd.xml
    |   `-- pmd.xml
    |-- pdepend/
    |   |-- dependencies.svg
    |   `-- overview-pyramid.svg
    `-- composer.phar
