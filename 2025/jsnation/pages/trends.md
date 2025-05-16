---
title: Trends
layout: center
---

# Part 3: key trends / success stories

---

<div class="flex flex-grow gap-8">

  <div>

  ## TypeScript

  10 years ago...

  - Flow (from Facebook), TypeScript but also CoffeeScript were popular JS "flavors"
  - Babel used to compile / bundle code for the browser
  - No clear winner at the time
  - Key moment: Angular was a complete rewrite of AngularJS in TypeScript


  </div>

  <div>

  ![logo](https://bestofjs.org/logos/typescript.dark.svg)

  </div>

</div>

<style>
img {
  width: 200px;
}
</style>  

---

#### TS in 2025: The defacto standard to write JS code!

The new runtimes using TS by default:

| 2018 | ![logo](https://bestofjs.org/logos/deno.dark.svg) | [Deno](https://deno.com/) |
| --- | --- | --- |
| 2021 | ![logo](https://bestofjs.org/logos/bun.dark.svg) | [Bun](https://bun.sh) |

Two exciting news from 2024:

<div class="flex items-center">

<svg viewBox="0 0 13 7" class="inline w-auto relative mr-3" aria-hidden="true" height="30"><path d="M0,2h2v-2h7v1h4v4h-2v2h-7v-1h-4" fill="#083344"></path><g fill="#f7df1e"><path d="M1,3h1v1h1v-3h1v4h-3"></path><path d="M5,1h3v1h-2v1h2v3h-3v-1h2v-1h-2"></path><path d="M9,2h3v2h-1v-1h-1v3h-1"></path></g></svg>

A new package registry from the Deno team that supports TS natively.
</div>

TypeScript is coming to [Node.js 23](https://www.totaltypescript.com/typescript-is-coming-to-node-23)!

---

## Styling: From Bootstrap to headless components

The "CSS frameworks" era

- Started with Bootstrap
- Opinionated about the design
- consistent look-and-feel out of the box
- can be hard to customize (fighting CSS and conflicting classes!)

---

### CSS Pre-processors

Used to generate CSS from different languages adding features such as variables and functions

| 2010 | ![logo](https://bestofjs.org/logos/less.dark.svg) | [Less](http://lesscss.org/) |
| --- | --- | --- |
| 2010 | ![logo](https://bestofjs.org/logos/stylus.dark.svg) | [Stylus](https://stylus-lang.com/) |
| 2012 | ![logo](https://bestofjs.org/logos/sass.svg) | [Sass](https://github.com/sass/node-sass) |
| 2013 | ![logo](https://bestofjs.org/logos/postcss.dark.svg) | [PostCSS](https://postcss.org/): the one that survived |


---

### CSS-in-JS

Perfect for component-based applications:
- Scoped styles prevent conflicts
- Dynamic styles based on props/state
- Co-location of styles with components

Popular solutions:

| 2016 | ![logo](https://avatars.githubusercontent.com/u/20658825?v=3&s=50) | [Styled Components](https://styled-components.com/) |
| --- | --- | --- |
| 2017 | ![logo](https://avatars.githubusercontent.com/u/31557565?v=3&s=50) | [Emotion](https://emotion.sh/) |

---

Trade-offs:

- Runtime overhead
- Bundle size impact
- Learning curve
- Server-side rendering complexity

---


### The rise of headless components

Unstyled components with built-in accessibility

| 2020 | ![logo](https://avatars.githubusercontent.com/u/476009?v=3&s=50) | [React Aria](https://react-spectrum.adobe.com/react-aria/index.html) |
| --- | --- | --- |
| 2020 | ![logo](https://bestofjs.org/logos/headlessui.dark.svg) | [Headless UI](https://headlessui.com/) |
| 2021 | ![logo](https://bestofjs.org/logos/radix.dark.svg) | [Radix Primitives](https://radix-ui.com/primitives) |

Benefits:
- Separation of concerns
- Full customization
- Built-in accessibility

---

<div class="flex gap-8">

  <div class="flex-grow">

  ## TailwindCSS

  Atomic CSS approach:

  - Write styles directly in HTML
  - No CSS files to maintain
  - Consistent design system
  - Great DX with autocomplete
  - Build-time optimization

  Why TailwindCSS became a standard:

  - Great docs
  - Scale from small to large apps
  - Reuse knowledge across projects
  - Active community & ecosystem

  </div>

  <div>

  ![logo](https://bestofjs.org/logos/tailwindcss.dark.svg)
  
  </div>

</div>

<style>
  img {
    width: 200px;
  }
</style>  

---

#### The TailwindCSS Love/Hate Relationship

It still feels strange to rely on string concatenation within class names!

```html
<Command className="[&_[cmdk-group-heading]]:px-2 [&_[cmdk-group-heading]]:font-medium [&_[cmdk-group-heading]]:text-muted-foreground [&_[cmdk-group]:not([hidden])_~[cmdk-group]]:pt-0 [&_[cmdk-group]]:px-2 [&_[cmdk-input-wrapper]_svg]:size-5 [&_[cmdk-input]]:h-12 [&_[cmdk-item]]:px-2 [&_[cmdk-item]]:py-3 [&_[cmdk-item]_svg]:size-5">
  {children}
</Command>
```

---

### Great alternatives

Type safety + build-time processing

| 2021 | ![logo](https://bestofjs.org/logos/unocss.dark.svg) | [UnoCSS](https://unocss.dev/) from Anthony Fu |
| --- | --- | --- |
| 2022 | ![logo](https://bestofjs.org/logos/stylex.dark.svg) | [Stylex](https://emotion.sh/) from Meta |
| 2022 | ![logo](https://bestofjs.org/logos/panda.dark.svg) | [Panda](https://panda-css.com/) from ChakraUI Team |

The lesson: sometimes it's not the best concept that wins, but rather the best execution (ecosystem, documentation, and social media presence).


---

<div class="flex gap-8">

<div class="flex-grow">

### shadcn/ui components

The hottest project in 2023 and 2024!

Built on headless components:
- Easy to customize
- Copy-paste approach
- No NPM install needed
- Great DX with CLI

Ecosystem: CLI works with any registry
- [shadcn-vue](https://www.shadcn-vue.com/)
- [shadcn-svelte](https://www.shadcn-svelte.com/)
- [shadcn-solid](https://shadcn-solid.vercel.app/)

</div>

<div>

![logo](https://bestofjs.org/logos/shadcnui.dark.svg)

</div>

</div>

<style>
  img {
    width: 200px;
  }
</style> 

---

## Tooling: the need for speed

Not written in JS anymore but in Go or Rust

| 2016 | ![logo](https://bestofjs.org/logos/esbuild.dark.svg) | [esbuild](https://esbuild.github.io/) low level bundler |
| --- | --- | --- |
| 2020 | ![logo](https://bestofjs.org/logos/vite.dark.svg) | [Vite](http://vitejs.dev/) a key part of the eco-system! |
| 2021 | ![logo](https://bestofjs.org/logos/vitest.dark.svg) | [Vitest](https://vitest.dev/) the modern test runner |
| 2023 | ![logo](https://bestofjs.org/logos/biome.dark.svg) | [Biome](https://biomejs.dev/) the replacement of ESLint and Prettier |

More exciting tools being cooked at [Void0](https://voidzero.dev/), the company founded by Evan You.

- [Rolldown](https://rolldown.rs/)
- [OXC](https://oxc.rs/)
