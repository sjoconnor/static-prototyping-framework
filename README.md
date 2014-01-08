Prototyping
============================

Installing
----------

After cloning the project run a `bundle install` to ensure all gem dependencies are installed.

Basic Directory Structure
-------------------------

```bash
├── _site/
├── source/
|   ├── _includes/
|   ├── _layouts/
|   ├── artwork/
|   ├── fonts/
|   ├── javascripts/
|   ├── stylesheets/
|   ├── _config.yml
|   └── index.html
```

`_site/` is where the generated site will exists. Changes to a prototype should never be made here.

`source/` is where all changes should take place. Jekyll will use this directory to generate the site and place it inside the `_site` directory.

Running the an App
------------------

Once you have the project navigate into the `source` directory and run:

```bash
jekyll serve --watch
```

This will allow you to view any changes you make in real time by navigating to `localhost:4000` in your browser. Any time you make a change and save a file in the `source` directory Jekyll automatically update as needed.

Jekyll creates a directory at the root of the project called `_site` where it stores the static files of a site. This directory contains the website in static HTML, CSS, and JavaScript so that it can be given to anyone with a web browser and still function.

Convenience Tasks In Console
----------------------------

To generate the static site run:

```bash
jekyll build
```

To create a zip file of the site run the following with an optional filename. If no filename is provided it will use the current directory name:

```bash
rake package[optional_filename]
```

Resources
---------

For a better understanding of how Jekyll templates work take a look at [Liquid Templating](http://jekyllrb.com/docs/templates/).
