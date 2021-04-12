# J1 Starter Web

Jekyll meets Bootstrap - and makes a lot of friends. J1 Template combines
the best of OpenSource software for the Web and the Web site generator
`Jekyll`. J1 is OpenSource, and so are the packaged modules - no pain for
private or professional use. Explore this site to learn what's possible if
you go to the Jekyll Way.

**Create powerful modern Static Webs: Secure, Flexible and Fast.**

Have fun!

# Supported platforms

J1 is supported on all current x64-based OS:

* Windows 10, build >= 1903
* Windows WSL 2
* Linux, kernel version >= 4.15 (e.g. Ubuntu  18.x LTS)
* OSX, version >= 10.10.5 (Yosemite)

Note that 32-bit versions (x32) are generally NOT supported for all
platforms.

# Development languages and tools

To run the Development System for J1 Template, the following languages and
tools expected to be in place with your OS:

*   Ruby language, version >= 2.6 < 2.7
*   Javascript language (NodeJS), version >= 12.x < 13
*   NPM, version >= 6.14
*   YARN, version >= 1.22

# Setting up the project

Running the J1 template project is very simple:

* Clone the repo
* Setup the project
* Run and develop your web

J1 Project Structure
```
  ├──── .
  │     └─ _data  <1>
  │     └─ _includes <2>
  │     └─ _plugins <3>
  │     └─ assets <4>
  │     └─ collections <5>
  │     └─ pages <6>
  │     └─ utilsrv
  ├──── _config.yml <7>
  ├──── config.ru
  ├──── .gitattributes
  ├──── .gitignore
  ├──── favicon.ico
  ├──── Gemfile <8>
  ├──── index.html <9>
  └──── package.json <10>
```

* <1>   J1 Configuration data
* <2>   Asciidoc includes (global)
* <3>   Build-in plugins (Ruby)
* <4>   Assets for the Web
* <5>   Folder that contains all Blog Posts
* <6>   Folder that contains all Articles
* <7>   Central site configuration (Jekyll)
* <8>   Ruby Gemfile
* <9>   Homepage for the Web
* <10>  J1 Project file (NPM)


## Initialize the project

The task `setup` takes a while. Typically some minutes for the *first*
run (depending on the performances of your Internet connection and your
Desktop PC). A bunch of NPM modules and Ruby Gems gets downloaded, installed,
and linked for the project. See the setup task as an extended *install* and
*build* process to make your new website ready to use.

Let's start ...

``` sh
yarn setup
```

Because a lot of sub-tasks getting started for a (first) `setup`, see below
the output as a summary :

```
Setup project for first use ..
Bootstrap base modules ..
done.
Configure environment ..
done.
Create project folders ..
Create log folder ..
Create archived log folder ..
Create etc folder ..
done.
Bootstrap project modules ..
Bootstrap utility server modules ..
done.
Detect OS ..
OS detected: Windows_NT
Build site incremental ..
Configuration file: C:/J1Webs/starter/_config.yml
            Source: C:/J1Webs/starter
       Destination: C:/J1Webs/starter/_site
 Incremental build: enabled
      Generating...
    J1 QuickSearch: creating search index ...
    J1 QuickSearch: finished, index ready.
      J1 Paginator: autopages, disabled|not configured
      J1 Paginator: pagination enabled, start processing ...
      J1 Paginator: finished, processed 1 pagination page|s
                    done in 37.609 seconds.
 Auto-regeneration: disabled. Use --watch to enable.
.. build finished.
To open the site, run: yarn site
Done in 94.94s.
```

## Running the Starter Web

Running the Starter Web for development is done like so:

``` sh
yarn site
```

The task `site` does a lot for you; whatever is necessary for a full-stack
Web development. The task will put in place all needed CSS and JS components,
build the Web content, and finally run the webite in a browser.

Go, go, go ..

```
yarn run v1.22.10
$ run-p -s site:*
Startup the site ..
UTILSRV disabled. Not started.
Configuration file: C:/J1Webs/starter/_config.yml   <1>
            Source: C:/J1Webs/starter   <2>
       Destination: C:/J1Webs/starter/_site   <3>
 Incremental build: enabled
      Generating...
    J1 QuickSearch: recreate index disabled.
      J1 Paginator: autopages, disabled|not configured
      J1 Paginator: pagination enabled, start processing ...
      J1 Paginator: finished, processed 1 pagination page|s
                    done in 9.618 seconds.
 Auto-regeneration: enabled for '.'
LiveReload address: http://localhost:40001    <5>
    Server address: http://localhost:40000/   <4>
  Server running... press ctrl-c to stop.
        LiveReload: Browser connected   <6>
```

* <1> The configuration file for the builder engine _Jekyll_
* <2> The project folder
* <3> The *WebRoot* folder for your website creaated
* <4> The *URL* to access the web
* <5> A *LiveReloader* is started and listens on port *40001*
* <6> A webbrowser has been started automatically and the *LiveReloader*
    is connected

Your *default* web browser is automatically started, and the website gets
loaded.

## Reset the Project

To start from the beginning, you can reset the project to the factory state.
The top-level task `reset` does the resetting work for you
and cleans up each and everything except the Git repo and the NPM modules
folder `node_modules` stored in the project root. Both are kept untouched
by a reset.

``` sh
yarn reset
```

The cleanup runs some tasks for the root folder and in parallel sub-tasks
using Lerna for all packages:

``` sh
```

To reset the Development System *completely*, delete the folder `node_modules`
manually and start from scratch by running the `setup` task again:

``` sh
yarn setup
```

Happy Jekylling!
