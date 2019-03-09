# GreenLife Family Farms Website

Client:   Jeff & Dustin

Project: A temporary website to promote their launch event.


## Overview
We're making a website for GreenLife Family Farm's launch event on May 18th. They want to start promoting the event with their website asap, so our deadline is March 14th for this iteration of the site.

## Planter Guide

Get started with Planter by downloading the zip (probably the best option for new projects so you can initialize your own git history.)

In `planter/`, run `npm install` to install all the dev dependencies for the project (i.e. Gulp & some Gulp utilities).

To start watching/building your source files as you work, just run `gulp` in your terminal.

That's it! Start by using the default setup and write your styles in `style.scss` and your JavaScript in `main.js`.

Feel free to add a deeper layer of organization with more directories in `js/` or `styles/` and import them into the main respective source files; don't worry the gulp task will handle it and still compile your client-side output files!

## More Info

Some extra info about Planter that might help, especially if you haven't some of the included tools like Gulp before.

### gulpfile.js

The `gulpfile` in the main directory is written in Gulp 4.x syntax and ready to go with the default file structure. It includes the core build tasks: `styles`, `js`. These tasks work to look at an entry point file and build a single `.css` or `.js` file to serve on the client side (in `/pub`).

The two watch tasks, `watchStyles` and `watchJS`, run the core build tasks anytime the source files change.

There are also some helper build tasks: `buildStyles`, `buildJS`, and `build`. The first two simply let both the core build tasks _and_ the watch tasks run in parallel. The `build` task then runs _those_ two build helper tasks run in parallel. This allows you to run a single task, `build`, to watch and build all your style and JS code. Note: `build` is set to the default task, so running just `gulp` in your terminal will get the job done.

The tasks are setup to use the `paths` object, which you would customize if you were to change the directory structure, or want to rename any input/output files.

#### Styles
The `styles` task uses the `src/styles/**/*.scss` glob as the entry point for the source. This means it's getting _all_ the `.scss` files in `src/styles/` and piping them to the sass plugin for compilation into an output `.css` file.

#### JavaScript
The `js` task uses `src/js/main.js` as the entry point by default. It uses [Browserify](http://browserify.org/) to bundle all the dependencies that stem from `main.js` into a single file, `bundle.js`, by default. [Babelify](https://github.com/babel/babelify) is also used to convert any ES6+ flavored code you write into ES5 so Browserify can make use of it (i.e. changing your `import` syntax to `require`).
