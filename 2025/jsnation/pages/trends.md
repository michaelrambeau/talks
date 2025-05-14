---
title: Trends
layout: center
---

# Part 3: key trends / success stories

---

## TypeScript

10 years ago...

- Flow (from Facebook), TypeScript but also CoffeeScript were popular JS "flavors"
- Babel used to compile / bundle code for the browser
- No clear winner at the time
- Key moment: Angular was a complete rewrite of AngularJS in TypeScript

---

#### TS in 2025: The defacto standard to write JS code!

New runtimes using TS by default:

| ![logo](https://bestofjs.org/logos/deno.dark.svg) | [Deno](http://lesscss.org/) | 2018 |
| --- | --- | --- |
| ![logo](https://bestofjs.org/logos/bun.dark.svg) | [Bun](https://stylus-lang.com/) | 2021 |


TypeScript is coming to [Node.js 23](https://www.totaltypescript.com/typescript-is-coming-to-node-23)!

[JSR](https://deno.com/blog/jsr-is-not-another-package-manager): a new package registry from the Deno team that supports TypeScript natively.

<style>
  img {
    width: 50px;
  }
</style>  

---

## Styling: From Bootstrap to headless components

The "CSS frameworks" era

- Started with Bootstrap
- Opinionated about the design
- consistent look-and-feel out of the box

- can be hard to customize (fighting CSS and conflicting classes!)
- bloated code, external dependencies

```html
<button class="btn btn-primary">Push me</button>
```

---

### CSS Pre-processors

Used to generate CSS from different languages adding features such as variables and functions

| ![logo](https://bestofjs.org/logos/less.dark.svg) | [Less](http://lesscss.org/) | 2010 |
| --- | --- | --- |
| ![logo](https://bestofjs.org/logos/stylus.dark.svg) | [Stylus](https://stylus-lang.com/) | 2010 |
| ![logo](https://bestofjs.org/logos/sass.svg) | [Sass](https://github.com/sass/node-sass) | 2012 |
| ![logo](https://bestofjs.org/logos/postcss.dark.svg) | [PostCSS](https://postcss.org/): the one that survived | 2013 |


---

### CSS-in-JS

SPA often require dynamic styling

Play well with components

| ![logo](https://avatars.githubusercontent.com/u/20658825?v=3&s=50) | [Styled Components](https://styled-components.com/) | 2016 |
| --- | --- | --- |
| ![logo](https://avatars.githubusercontent.com/u/31557565?v=3&s=50) | [Emotion](https://emotion.sh/) | 2017 |

---


### The rise of headless components

- Unstyled! Provide the essential functionality and logic without being tied to a specific user interface, allowing for extensive customization and flexibility.
- Composable and flexible
- Accessibility features built-In

- [React Aria](https://react-spectrum.adobe.com/react-aria/index.html)
- [Headless UI](https://headlessui.com/)
- [Radix Primitives](https://radix-ui.com/primitives)

---

## TailwindCSS

With TailwindCSS, you don't write CSS code, you combine class utilities in your HTML (Atomic CSS)

Benefits:

- it scales well, no matter the size of your application
- it has became a kind od standard, developers can re-use their knowledge within projects

---

#### TailwindCSS love/hate relation

It's still feels weird to rely on the concatenation of strings inside class names!

Great alternatives, providing type safety and running at build time:

| ![logo](https://bestofjs.org/logos/unocss.dark.svg) | [UnoCSS](https://unocss.dev/) from Anthony Fu | 2021 |
| --- | --- | --- |
| ![logo](https://bestofjs.org/logos/stylex.dark.svg) | [Stylex](https://emotion.sh/) from  Meta | 2022 |
| ![logo](https://bestofjs.org/logos/panda.dark.svg) | [Panda](https://panda-css.com/) from ChakraUI Team | 2022 |


The lesson: sometimes it's not the best concept that wins, it's the best execution (ecosystem, docs, buzz on social medias...)

<style>
  img {
    width: 50px;
  }
 </style> 

---

## shadcn/ui components

![logo](https://bestofjs.org/logos/shadcnui.dark.svg) The hottest project in 2023 and 2024!

A collection of components built on top of headless solutions, easy to customize

A new way to distribute code (the registry, no more NPM install)

<style>
  img {
    width: 20px;
    display: inline;
  }
</style> 

---

## Tooling: the need for speed

Not written in JS anymore but in Go or Rust

| ![logo](https://bestofjs.org/logos/esbuild.dark.svg) | [esbuild](https://esbuild.github.io/) low level bundler| 2016 |
| --- | --- | --- |
| ![logo](https://bestofjs.org/logos/vite.dark.svg) | [Vite](http://vitejs.dev/) a key part of the eco-system! | 2020 |
| ![logo](https://bestofjs.org/logos/vitest.dark.svg) | [Vitest](https://vitest.dev/) the modern test runner | 2021 |
| ![logo](https://bestofjs.org/logos/biome.dark.svg) | [Biome](https://biomejs.dev/) the replacement of ESLint and Prettier | 2023 |

More exciting tools being cooked at [Void0](https://voidzero.dev/), the company founded by Evan You.

- [Rolldown](https://rolldown.rs/)
- [OXC](https://oxc.rs/)

<style>
  img {
    width: 50px;
  }
</style>  



