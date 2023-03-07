---
title: "Typewind: The magic of Tailwind combined with the safety of Typescript"
seoDescription: "Typewind: Tailwind CSS with type-safety and zero-runtime overhead. Autocomplete, prevent typos, and catch errors at compile time"
datePublished: Wed Jan 25 2023 13:10:20 GMT+0000 (Coordinated Universal Time)
cuid: cldboozbg000j09ladctn6iwz
slug: typewind-the-magic-of-tailwind-combined-with-the-safety-of-typescript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674651899791/52be5396-3b97-4ebb-99db-17c4be2eefb2.png
tags: web-development, typescript, frontend-development, tailwind-css

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674651855860/13a5eb54-63b2-4dc8-b78d-617c8a3b0adf.png align="center")

Well, the people who've read my previous articles know how much I love type-safety, hence someone who loves the [t3 stack](https://livecode247.com/why-t3-stack). Here's [Typewind](https://typewind.vercel.app), a **typesafe** and **zero-runtime** version of Tailwind CSS, a utility-first CSS framework that can be composed to build any design, directly in your markup.

## What does Typewind do?

Typewind is a powerful utility-first CSS framework that combines the magic of Tailwind with the safety of Typescript. It provides a typesafe environment over Tailwind CSS, enabling developers to work with autocomplete, prevent typos, and catch errors at compile time. With zero runtime overhead, Typewind generates custom type definitions based on your app's `tailwind.config.js` file, making it a top choice for developers who value type-safety. Here's an example of how Typewind works:

[https://twitter.com/Mokshit06/status/1617880004846825474](https://twitter.com/Mokshit06/status/1617880004846825474)

```typescript
import { tw } from "typewind";

export default function Button() {
    return (
        <button className={tw.}></button>
    )
}
```

The moment you type `tw.`, you will get autocomplete like so, based on your own custom `tailwind.config.js`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674663236218/5f9613b6-e151-40f3-868d-6566be5fc2ff.png align="center")

And, the moment you make a typo:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674663315897/cfd990fa-e131-4f1e-bf09-eb2935256800.png align="center")

And it has absolutely zero overhead runtime! Will talk a little more about the features below, but before that, let me talk about how this started!

## Origin

The whole thing started with one tweet.

[https://twitter.com/stolinski/status/1613699772111638530](https://twitter.com/stolinski/status/1613699772111638530)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674651739185/b39b37fa-5ad6-46df-a1e7-1e609c0f7b86.png align="center")

Then [Colin McDonnell](https://twitter.com/colinhacks) tweeted on what tailwind with type safety and proper autocompletion would look like.

[https://twitter.com/colinhacks/status/1615154756204523521](https://twitter.com/colinhacks/status/1615154756204523521)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674651771996/779a5f25-b3fd-4f9d-b82b-17d4dac0a93a.png align="center")

[Mokshit](https://mokshitjain.co), the creator of Typewind, sent me this tweet and both of us, at first look were having confused thoughts but the more and more we saw it, the more and more we started getting convinced of it. Looks like [Theo](https://twitter.com/t3dotgg/status/1615232346231558147?s=20&t=I5tEkOkmymKw31I4_7YT0A) had similar thoughts.

We discussed it for some time and he decided to start working on it. Overnight, he was done with the transpilation part and I was just hovering along with him, looking at the things which were being done understanding only 70% of the things happening.

I started working on the docs and working a little on the tailwind transformers started getting me interested in build tools (probably something I want to give a try in the future).

Fast forward to just a few days later, he was done building the package and I was done setting up the docs and the examples and decided to release. However, we had one issue. We couldn't think of a logo. After playing around for hours with different combinations, I thought of a wavy line under wind but said it looked bad and discarded it. Turns out only the font and the structure of the wavy line was bad cause the final version turned out way better.

![Typewind Logo](https://cdn.hashnode.com/res/hashnode/image/upload/v1674646321258/70dda6a9-7fd4-47ff-ac3a-b6084b91aef2.png align="center")

He released it overnight and it got a lot more response than we had expected! So here's about Typewind, and how you can get started with it:

## Features

* Zero runtime
    
* Type-safety and auto-completion
    
* CSS docs based on your config
    
* Apply variants to multiple styles at once
    
* No need for additional editor extensions
    
* Catches errors at compile time
    

Typewind, generated type definitions on Tailwind classes custom to your app's `tailwind.config.js` after running the `npx typewind generate` command.

Typewind has currently been tested to work with Vite (React) and Next.JS and you can find them in the [examples](https://typewind.vercel.app/docs/examples/vite).

## Getting Started

The [installation page in the docs](https://typewind.vercel.app/docs/installation) is a very good place to start with Typewind.

### Installation

Install via your favourite package manager (npm/yarn/pnpm).

```bash
npm install typewind
```

### Generate Type Definitions

```bash
npx typewind generate
```

This will go through your `tailwind.config.js` and generate types and css docs custom to your app.

### Setup with Next.JS

After setting up [Tailwind](https://tailwindcss.com/docs/installation), make the following changes:

1. Add a `.babelrc` with the following contents:
    

```json
{
  "presets": ["next/babel"],
  "plugins": ["typewind/babel"]
}
```

1. Add transformer to your Tailwind Config
    

```javascript
const { typewindTransforms } = require('typewind/transform');
 
/** @type {import('tailwindcss').Config} \*/
module.exports = {
  content: {
    files: ['./src/**/*.{js,jsx,ts,tsx}'],
    transform: typewindTransforms,
  },
};
```

And you're good to go! Just run `npm run dev` next time and you should be able to use Typewind inside your app.

### Setup with Vite

Make the same change in the `tailwind.config.js` file as mentioned in the NextJS example, but the babel change has to be done in the `vite.config.js` like so:

```javascript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react({ babel: { plugins: ['typewind/babel'] } })],
});
```

And, you'll be done setting up Typewind in your Vite application.

## Usage

Here's just a trailer to show you what it's capable of:

```typescript
import { tw } from 'typewind';
 
export default function App() {
  return (
    <div
      className={tw.flex.items_center.justify_center.h_screen.bg_white.text_["#333"].dark(tw.bg_black.text_white)}>
      <h1 className={tw.text_xl.sm(tw.text_3xl).md(tw.text_4xl).font_bold}>
        Hello World
      </h1>
    </div>
  );
}
```

### Applying Normal Tailwind Classes

All the utility tailwind classes are available in the `tw` proxy, and can be chained one after another. They can be found in the [Tailwind Docs](https://tailwindcss.com/docs/utility-first). The `-` in the tailwind classes are replaced with `_` (for eg. `bg-red-500` can be accessed as `tw.bg_red_500`)

```typescript
import { tw } from 'typewind';
 
export default function Button() {
  return (
    <button className={tw.bg_blue_500.text_white.rounded.py_3.px_4}>
      Click Me
    </button>
  );
}
```

### Applying Tailwind Modifiers

[Pseudo-classes](https://tailwindcss.com/docs/hover-focus-and-other-states#pseudo-classes) like `:hover` and `:focus`, [Pseudo-elements](https://tailwindcss.com/docs/hover-focus-and-other-states#pseudo-elements) like `::before`, `::after`, `::placeholder` and `::selection`, [Media and feature queries](https://tailwindcss.com/docs/hover-focus-and-other-states#media-and-feature-queries) and [Attribute Selectors](https://tailwindcss.com/docs/hover-focus-and-other-states#attribute-selectors) are available as a function (for eg. `:hover` can be accessed as `tw.hover(tw.some_class)` )

Typewind also have a `dark` function which is used to apply styles when the user is in dark mode.

```typescript
import { tw } from 'typewind';
 
export default function Button() {
  return (
    <button
      className={tw.bg_blue_500
        .hover(tw.bg_blue_600)
        .text_white.rounded.py_3.px_4.md(tw.py_4.px_5)
        .dark(tw.bg_sky_900.hover(tw.bg_sky_800))}
    >
      Click Me
    </button>
  );
}
```

> Note that Typewind does not have `tw.2xl()` but has `tw._2xl()` because object keys cannot start with a number 🫠

### Applying Tailwind Arbitrary Values

Tailwind JIT Mode introduced the feature of arbitrary values. You could now apply classes like `bg-[#2977f5]` and specify arbitrary values for classes by yourself. This can be done with Typewind as well!

```typescript
import { tw } from 'typewind';
 
export default function App() {
  return (
    <button className={tw.text_['20px'].py_3.px_4.bg_blue_500}>Click Me</button>
  );
}
```

## Why Typewind over Tailwind Intellisense?

This has been answered by Mokshit in this tweet:

[https://twitter.com/Mokshit06/status/1617506874773082112?s=20&t=erkUIb\_bUjty0KfXzGlrDw](https://twitter.com/Mokshit06/status/1617506874773082112?s=20&t=erkUIb_bUjty0KfXzGlrDw)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674663639622/c6b3ec29-49d6-444e-8150-c40706500d22.png align="center")

## Outro

Hope this gets you interested in getting started with Typewind, and gets you to use it in your next project!

%[https://github.com/mokshit06/typewind]