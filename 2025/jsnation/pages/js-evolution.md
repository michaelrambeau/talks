---
title: JavaScript's Evolution
layout: center
---

# Part 1: A Quick Overview of JavaScript's Evolution

---

## The Early Days: 1995-2005

JavaScript: a simple "toy" language for form validation

Limited browser support, basic DOM manipulation

---

### Vintage HTML/JS

```html
<FORM NAME="contactForm" onSubmit="return validateForm()">
  <INPUT TYPE="text" NAME="email">
  <INPUT TYPE="submit" VALUE="Send">
</FORM>

<SCRIPT LANGUAGE="JavaScript">
<!--
function validateForm() {
  var form = document.forms[0];
  var email = form.elements["email"].value;
  if (email == "") {
    alert("Please enter your email!");
    return false;
  }
  return true;
}
//-->
</SCRIPT>
```

---

## The Ajax Revolution (2005)

Enabled rich browser applications

Popular libraries:
- [Prototype.js](http://prototypejs.org/) and Script.aculo.us
- [Mootools](https://mootools.net/)
- [Dojo](https://dojotoolkit.org/)
- [YUI](https://yuilibrary.com/)

<div class="flex items items-center gap-4">
![prototype](http://prototypejs.org/images/header-logo.png)
![scriptaculous](https://duckduckgo.com/i/f30e7f53.png)
![yui](https://duckduckgo.com/i/068ede8a.jpg)
![Mootools](https://duckduckgo.com/i/e241bfd9.png)
</div>

---

#### jQuery Won the Battle!

Released in 2006, became ubiquitous

- Clean API, excellent docs
- Solved browser compatibility
- Integrated with WordPress

![jQuery](https://api.jquery.com/wp-content/themes/jquery/images/logo-jquery.png)

---

## JavaScript Moves to the Server

Node.js (2009) by Ryan Dahl

Made server-side JavaScript easy

NPM: most popular package manager

<div class="flex flex-row gap-8">
<img src="https://bestofjs.org/logos/nodejs.svg" width="100" />
<img src="https://bestofjs.org/logos/npm.svg" width="100" />
</div>

---

### Node.js ecosystem

Rich tooling ecosystem:
- Build: Grunt, Gulp, Webpack
- Transpilers: CoffeeScript, Babel
- Linters: ESLint
- Testing: Mocha, Jest

<div class="flex gap-4 items-center">
![logo](https://bestofjs.org/logos/coffeescript.dark.svg)
![logo](https://bestofjs.org/logos/gulp.dark.svg)
![logo](https://bestofjs.org/logos/babel.dark.svg)
![logo](https://bestofjs.org/logos/eslint.dark.svg)
![logo](https://bestofjs.org/logos/webpack.dark.svg)
![logo](https://bestofjs.org/logos/mocha.dark.svg)
![logo](https://bestofjs.org/logos/jest.dark.svg)
</div>

<style>
  img{
    width: 50px;
    height: 50px;
  }
</style>

---

## The SPA Golden Age

AJAX enabled Single Page Applications

Key features:
- Browser-based, no page reloads
- Static hosting
- JSON APIs (REST, GraphQL, RPC)

---

### The New Hot UI Libraries

Pioneers of client-side "MVC":

| 2010 | ![logo](https://bestofjs.org/logos/backbone.svg) | Backbone |
| --- | --- | --- |
| 2010 | ![logo](https://avatars.githubusercontent.com/u/3863375?v=3&s=50) | Knockout |
| 2010 | ![logo](https://bestofjs.org/logos/angularjs.svg) | AngularJS |
| 2011 | ![logo](https://bestofjs.org/logos/ember.svg) | Ember |

---

Three major frameworks emerged:

| 2013 | ![logo](https://bestofjs.org/logos/react.svg) | React |
| --- | --- | --- |
| 2013 | ![logo](https://bestofjs.org/logos/vue.svg) | Vue.js |
| 2014 | ![logo](https://bestofjs.org/logos/angular.svg) | Angular 2 |

<style>
  img {
    width: 50px;
  }
</style> 

---

### SPA Challenges

- Performance at scale
- SEO
- Frontend/backend sync

---

## The Meta-Framework Era

Full-stack frameworks with SSR, routing, data fetching

| 2016 | ![logo](https://bestofjs.org/logos/nextjs.dark.svg) | [NextJS](https://nextjs.org) |
| --- | --- | --- |
| 2016 | ![logo](https://bestofjs.org/logos/nuxt.svg) | [Nuxt](https://nuxt.com/) |
| 2020 | ![logo](https://bestofjs.org/logos/remix.dark.svg) | [Remix](https://remix.run/) |
| 2020 | ![logo](https://bestofjs.org/logos/svelte.svg) | [SvelteKit](https://svelte.dev/docs/kit) |
| 2021 | ![logo](https://bestofjs.org/logos/solid.svg) | [SolidStart](https://start.solidjs.com/) |

<style>
img {
  width: 50px;
}
</style> 

---

New paradigms:

- Server Components (React, Vue)
- Seamless frontend/backend
- PHP-like simplicity
