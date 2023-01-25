# Typewind: The magic of Tailwind combined with the safety of Typescript

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674651855860/13a5eb54-63b2-4dc8-b78d-617c8a3b0adf.png align="center")

Well, the people who've read my previous articles know how much I love type-safety, hence someone who loves the [t3 stack](https://livecode247.com/why-t3-stack). Here's [Typewind](https://typewind.vercel.app), a **typesafe** and **zero-runtime** version of Tailwind CSS, a utility-first CSS framework that can be composed to build any design, directly in your markup.

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
  "presets": [],
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

There are a few usage cases, just like in Tailwind and all of them can be found in detail in the documentation, and it would be redundant to write them again in this article. But here's just a trailer to show you what it's capable of:

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

## Outro

Hope this gets you interested in getting started with Typewind, and gets you to use it in your next project!

%[https://github.com/mokshit06/typewind]