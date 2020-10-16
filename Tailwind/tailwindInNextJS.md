# How to setup Tailwind in a new NextJS app

### Create New Next App

It may seem obvious, but the best place I find to start is at the beginning.

So lets create that shiny new project, I use Yarn these days, I've found it is faster and have only once needed to use NPM as one library wasn't supported.

```
	$ yarn create next-app <project-title>
```

Once we have the launchpad setup, I like to do a safety check just to make sure it was created properly, if it's a package its checking the -version to ensure it's installed.

But for a new project I like to kick off the server

```
	$ yarn dev
```

I call this a safety check because if you create a new app, start building and then something hasn't installed properly it can cause elevated heart rates and sometimes unsafe environments for technology within arms reach (haha!).

---

We should then have a folder structure like the following

```
root-folder
 > .next
 > node_modules
 > pages
    ├── api
    │   └── hello.js
    ├── _app.js
    └── index.js
 > public
    ├── favicon.ico
    └── vercel.svg
 > styles
    ├── globals.css
    └── Home.modules.css
 ─ .gitignore
 ─ package.json
 ─ README.md
 ─ yarn.lock
```

I won't be going over what files and folders do what, that is definitely for another lesson as I absolutely 💜 💜 💜 Next.JS and have a deep dive planned soon.

---

## Installation

Firstly let's remove all our CSS imports at the beginning of the file, and anything in the code with styles reference `className={styles.<style>}`

As this page is being rebuilt I am more likely to just delete all the code and start fresh anyway, but each to their own.

Then kick off by installing the package

```
	$ yarn add --save-dev tailwindcss postcss-preset-env
```

Remember to follow that up with your version check to ensure we don't have any gotchya creep up later on

```
	$ yarn -v tailwind
```

I know most of you don't do this, but that's because you've probably not been caught out for 30 mins wondering why code doesn't work only to find out that the package didn't install.

As the docs say 'Now the fun begins!'

Initialise tailwind with the NPX command

```
	npx tailwindcss init
```

(at this stage I'm not sure about yarn with NPX use, although I am investigating and if you know the answer do leave a comment below)

Once that has run, we need to create ourselves the `postcss.config.js` file in the root of our directory.

We should be left with something like this now

```
root-folder
 > .next
 > node_modules
 > pages
    ├── api
    │   └── hello.js
    ├── _app.js
    └── index.js
 > public
    ├── favicon.ico
    └── vercel.svg
 > styles
    ├── globals.css
    └── Home.modules.css
 ─ .gitignore
 ─ package.json
 ─ postcss.config.js
 ─ README.md
 ─ yarn.lock
```

And in `postcss.config.js` add

```js
module.exports = {
	plugins: ["tailwindcss", "postcss-preset-env"],
};
```

Then clear out the `styles/globals.css` file we don't need those anymore, and replace with the Tailwind imports

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

And delete the `Home.module.css` file completely.

---

And for the setup of Tailwind in a Next.JS app thats completed!

If you `yarn dev` and run the server you'll notice your app defaults to a styleless app and this is where I say **HERE COMES THE _FUN_ PART**
