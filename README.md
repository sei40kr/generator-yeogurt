<img src="http://i.imgur.com/obNKseX.png" />

# Yeogurt Generator [![Build Status](https://secure.travis-ci.org/larsonjj/generator-yeogurt.png?branch=master)](https://travis-ci.org/larsonjj/generator-yeogurt) [![NPM version](https://badge.fury.io/js/generator-yeogurt.png)](http://badge.fury.io/js/generator-yeogurt)

A [Yeoman](http://yeoman.io) generator for creating a sensible structure to front-end work.


## Getting Started

- First off, You will need to have [Node.js](http://nodejs.org/) `>= 0.10` installed. <br>
- Be sure to install yeoman of course! `npm install -g yo` <br>
- Install the generator: `npm install -g generator-yeogurt` <br>
- Run the generator: `yo yeogurt`

## Features

**Available Scaffolding Options:**

- Project/Site naming
- CSS Preprocessing with [LESS](http://lesscss.org/) or [SCSS](http://sass-lang.com/)
- Modular JavaScript with [RequireJS](http://requirejs.org/) or [Browserify](http://browserify.org/)
- IE8+ Support via [HTML5shiv](https://github.com/aFarkas/html5shiv) and [RespondJS](https://github.com/scottjehl/Respond)
- JavaScript Linting with [JSHint](http://www.jshint.com/)
- Default ignores for [Git](http://git-scm.com/) or [SVN](http://subversion.apache.org/)
- Build deployment to FTP server

**Included by default:**

- Template inspiration from [HTML5 Boilerplate](http://html5boilerplate.com/)
- [Jade](http://jade-lang.com/) markup templating
- Feature detection with [Modernizr](http://modernizr.com/)
- Built in preview server with LiveReload
- [.editorconfig](http://editorconfig.org/) for consistent coding styles within text editors
- JavaScript unit testing with [Jasmine](http://jasmine.github.io/) and [Karma](http://karma-runner.github.io/0.10/index.html) 
- Automatic build process that includes concatenation, image optimization, CSS and HTML minification, and JS uglification.
- Dynamic Dashboard - auto-generated dashboard for your site
- [Sourcemaps](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/) for both JavaScript and SCSS/LESS

## Grunt Tasks
- `grunt serve`<br>
Starts up a development server that watches for local file changes and automatically reloads them to the browser.

- `grunt test`<br>
Runs JSHint and Mocha to lint and unit test JavaScript, respectively.

- `grunt build`<br>
Builds out an optimised site through minification of CSS and HTML, as well as  uglification and optimisation(RequireJS) of Javascript.

- `grunt zip`<br>
Runs `grunt build` and compresses the entire site to a ZIP file

- `grunt deploy`<br>
Runs `grunt zip` and pushes both production-ready files and zip file to a specified FTP server


## Sub-Generators

Available sub-generators:

* [yeogurt:markup](#markup)
* [yeogurt:script](#script)
* [yeogurt:style](#style)

**Note: Generators are to be run from the root directory of your app.**

### Markup
Creates jade file within the `dev/markup/pages` folder by default or within another folder using the `--type` option.

Example:
```bash
## Page
yo yeogurt:markup mypage --type=page

## Template
yo yeogurt:markup mytemplate --type=page --template=one-column

## Helper
yo yeogurt:markup myhelper --type=helper

## Component
yo yeogurt:markup mycomponent --type=component
```

### Script
Creates module script within the `dev/scripts/modules` folder by default or a inline script using the `--inline=true` option.

Example:
```bash
## Module
yo yeogurt:script myscript

## Inline
yo yeogurt:script myscript --inline=true
```

### Style
Creates stylesheet file within the `dev/styles/partials` folder by default or inside a specified folder using the `--folder` option.

Example:
```bash
## Create mystyle file within dev/styles/partials folder
yo yeogurt:style mystyle

## Create mystyle file within dev/styles/base folder
yo yeogurt:style mystyle --folder=base
```

## Dynamic Dashboard
Here is what the dashboard looks like when you run `grunt serve`:<br>
![](http://i.imgur.com/yW4QC3e.png =650x)

It is 'dynamic' because it is generated at compile time using comments placed at the top of development files. An example of these comments in a template file is as follows:

```
//- Dashboard Data
    !##
    {
        "status": "development",
        "blocks": [
            {
                "blockName": "content",
                "width": "100px",
                "height": "100px",
                "bgcolor": "#9d9d9d",
                "textColor": "#fff",
                "fontSize": "10px"
            }
        ]
    }
    ##!
```
For Jade pages, components, templates, and helpers, these comments create the ability to pass data directly to the dashboard. In the above code example, we are setting a template file's status to be in 'development' and are adding a content block with a name of 'content' and a couple of CSS properties.

### Data Properties

##### Pages, Helpers, Templates, and Components
property:

- `status` [String]

possible values:

- `blocked`: When development is blocked from continuing
- `queued`: Ready to be assigned to a developer
- `development`: Development is under way
- `qa`: Being tested and evaluated for correct implementation
- `review`: 'Under review from code quality stand-point',
- `integration`: Being integrated to final development environment (Usually for Content Managment Systems)
- `Complete`: 'Development is complete'

##### Templates Only
property:

- `blocks` [Array]

possible values [Each object in Array]:

- `blockName`: Name that will be displayed within the created block
- `width`: Width of block
- `height`: Height of block
- `bgcolor`: Background color of block
- `textColor`: Color of text within block
- `fontSize`: Size of font within block

##### Helpers and Components Only
property:

- `markup` [String]

possible values

- `Any Jade Markup`

#### Huh?

A bit confused? No worries, I recommend generating a test project and taking a look at the jade files within the generated pages, components, templates, and helpers folders. They will have some simple examples of what's possible and you can see your changes in real time if you run `grunt serve`.

Also, feel free to open up an issue if you think something is too confusing or can be improved.

## Contributing to this project

Anyone and everyone is welcome to contribute. Please take a moment to
review the [guidelines for contributing](CONTRIBUTING.md).

* [Bug reports](CONTRIBUTING.md#bugs)
* [Feature requests](CONTRIBUTING.md#features)
* [Pull requests](CONTRIBUTING.md#pull-requests)

## Release History

See [Changelog](https://github.com/larsonjj/generator-yeogurt/blob/master/CHANGELOG.md)

## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/larsonjj/generator-yeogurt/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
