GoApp
=====
[under development]
A framework for creating, building, testing, and managing Go applications with features that include
 - configuration files dependent on the specified environment (think production.json, development.json, test.json)
 - a set of gorake tasks for initializing, building, testing, and managing a Go application and it's sub-packages
 - a set of gorake tasks for bootstrapping, migrating, and initializing application databases (think boostrap, migrate, reset)
 - a testing framework that manages the setup and teardown of the test database between tests

Installation
============
With a standard ruby/bundle project workspace set up, add the following to your project Gemfile
```
gem 'goapp', :git => 'git://github.com/snormore/goapp.git'
```

Usage
=====
Create a new project
```
goapp startproject github.com/foouser/barproject
```
which creates a project wih the structure
```
barproject
|-- cfg
  |-- base.json
  |-- development.json
  |-- production.json
  |-- test.json
-- src
  |-- github.com
    |-- foouser
      |-- barproject
        |-- app.go
-- pkg
-- bin
```
NOTE you should add `bin` and `pkg` directories to your .gitignore file or the ignore file of the vcs you're using.

Building your project
```
goapp build
```

Run your project
```
goapp run
```

Test your project
```
goapp test
```

Show available gorake commands
```
goapp
```
