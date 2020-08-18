# Babel

[Babel](https://babeljs.io/) is the compiler React uses to compile JSX down to browser readable JavaScript.

## Installation

To install Babel run

```
	<!-- yarn -->
	$ yarn global add babel-cli

	<!-- NPM -->
	$ npm install -g babel-cli
```

babel-cli provides command line access to the compiler

Again to check we have installed it correctly, run the version command

```
	$ babel --version
```

## Help

Once Babel has been installed you then have access to the **help** call to display all the Babel related options

```
	$ babel --help
```

## Init

If the project hasn't been initialised, kick it off by running

```
	<!-- yarn -->
	$ yarn init

	<!-- NPM -->
	$ npm init
```

This will cycle through the project initiation questions, and these will be the same regardless of if you are running Yarn or NPM

```
	name (application name):
	version (1.0.0):
	description:
	entry point (index.js):
	repository url:
	author:
	license (MIT):
```

This generates your package.json file in the root of the project, these fields can be updated at any time.

Next we need to add the packages needed in our program, and they can be installed together

```
	$ yarn add babel-preset-react babel-preset-env
```

-   babel-preset-react - is the react specific runtime.

-   babel-preset-env - is the preset manager that automatically converts the JSX down to the appropriate form of JavaScript i.e ES2015, ES2017, ES2020.

This will generate your Node Modules package, and a yarn/npm lock file. These files do not need to be touched or worried about, they basically sort themselves out.

Now we are ready to run Babel as we write JSX code and have it compile down to browser readable javascript.

This will depend on the folder structure of course, and here is my current template.

```
	<!-- Folder Structure -->

root-folder/
	├── node_modules
	├── public/
	│   ├── scripts/
	│   │   └── app.js
	│   └── index.html
	├── src
	│   └── app.js
	├── package.json
	└── yarn.lock
```

To kick off the Babel magic we need to identify where the JSX is being written and where its being compiled too.

```
	$ babel src/app.js --out-file=public/scripts/app.js --presets=env,react --watch
```

As you guessed it src/app.js is where we write the JSX; --out-file is the location Babel converts the to JavaScript, --presets are invoking the Babel extensions we installed that do all the work; and --watch is a watcher to reload and compile on save with each change made.
