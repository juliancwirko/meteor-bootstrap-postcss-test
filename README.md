## Meteor Bootstrap 4 Scss from Npm with PostCSS - playground

This is just a quick test and demo project which uses [PostCSS package](https://github.com/juliancwirko/meteor-postcss/tree/meteor-1.3-in-progress) and some PostCSS plugins to compile Scss provided by Bootstrap 4 from Npm package.

**For now with Meteor 1.3 you are not able to import and compile .scss files from `node_modules`. Here we use PostCSS and couple of its plugins to be able to install bootstrap from Npm and then import its .scss files from `node_modules` folder.**

### Run it locally

```bash
$ git clone https://github.com/juliancwirko/meteor-bootstrap-postcss-test.git
$ cd meteor-bootstrap-postcss-test
$ npm install
$ meteor
```

### What I've done here:

1. I use [juliancwirko:postcss](https://github.com/juliancwirko/meteor-postcss/tree/meteor-1.3-in-progress) PostCSS integration package for Meteor (in version 1.0.0-rc.10_1)
2. I use some PostCSS plugins. Take a look at `package.json` file at 'postcss' key. Here is the list: ["autoprefixer": "^6.3.4", "postcss-easy-import": "^1.0.1", "postcss-nested": "^1.0.0", "postcss-sassy-mixins": "^2.0.0", "postcss-simple-vars": "^1.2.0"]
3. I import all bootstrap .scss files in `client/main.css` file - yes it should be .css file not .scss
4. I import all Bootstrap javascript in `client/main.js` file (ES6 modules).
5. All is installed by `npm install bootstrap@4.0.0-alpha.2 --save`
6. We don't need `fourseven:scss` here!

### Benefits

Scss imports and compilation from `node_modules` without any additional work. (You can't do this now with Meteor 1.3) Bootstrap here is just a working example, there can be more other libs with styles attached.

This could be also a very good transition from projects based on Scss to full PostCSS stack without preprocessors. I think that Bootstrap will be written in PostCSS in the future too.

Besides Scss and Bootstrap you can use plenty other [PostCSS plugins](http://postcss.parts/).

### What doesn't work

I've tried it with Foundation 6 too. Unfortunatelly because Foundation 6 uses complicated mixins structures the PostCSS plugin responsible for [sassy mixins](https://github.com/andyjansson/postcss-sassy-mixins) can't manage it. We don't use a standard Scss compiler here, so it could be problematic in complicated structures. We use basic stuff like Sass-like variables, nesting, mixins, imports.

**This solution will not work in complicated use cases. But I'm sure it could be worked out somehow.**

### Please play with it

Let me know if you'll find something interesting. You can also comment here in the GitHub issues.
I'll try to do some more research too. I'll try to run Foundation 6 from Npm.

### ...

<img src="https://media.giphy.com/media/f1ohcPEHABwWY/giphy.gif" width="480" height="294" />
