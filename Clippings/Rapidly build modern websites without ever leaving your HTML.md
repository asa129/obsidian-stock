---
title: Rapidly build modern websites without ever leaving your HTML.
source: https://tailwindcss.com/
author:
  - "[[Tailwind CSS]]"
published: 
created: 2025-06-08
description: Tailwind CSS is a utility-first CSS framework for rapidly building modern websites without ever leaving your HTML.
tags:
  - clippings
  - tailwindcss
---
[Docs](https://tailwindcss.com/docs) [Blog](https://tailwindcss.com/blog) [Showcase](https://tailwindcss.com/showcase) [Plus](https://tailwindcss.com/plus?ref=top)

A utility-first CSS framework packed with classes like flex,pt-4,text-center and rotate-90 that can be composed to build any design, directly in your markup.

[Get started](https://tailwindcss.com/docs/installation)

[Get started](https://tailwindcss.com/docs/installation)

```
<div class="flex flex-col items-center p-7 rounded-2xl">
  <div>
    <img class="size-48 shadow-xl rounded-md" alt="" src="/img/cover.png" />
  </div>
  <div class="flex">

    <span>The Anti-Patterns</span>
    <span class="flex">
      <span>No. 4</span>
      <span>·</span>
      <span>2025</span>
    </span>
  </div>
</div>
```

![](https://tailwindcss.com/_next/static/media/cover.de1997f7.png)

Class Warfare The Anti-Patterns No. 4 · 2025

Why Tailwind CSS?

## Built for the modern web.

Tailwind is unapologetically modern, and takes advantage of all the latest and greatest CSS features to make the developer experience as enjoyable as possible.

Responsive design

Okay, it’s not exactly cutting edge, but just throw a screen size in front of literally any utility to apply it at a specific breakpoint.

Mobile

sm

md

lg

xl

![](https://tailwindcss.com/_next/static/media/responsive-1.fd2e9248.png) ![](https://tailwindcss.com/_next/static/media/responsive-2.8cfea49d.png) ![](https://tailwindcss.com/_next/static/media/responsive-3.e7467feb.png)

Entire house Beach House on Lake Huron

Entire house

Beach House on Lake Huron 2.66 (128 reviews) · Bayfield, ON

This sunny and spacious room is for those traveling light and looking for a comfy and cozy place to lay their head for a night...

Show more

![](https://tailwindcss.com/_next/static/media/responsive-1.fd2e9248.png) ![](https://tailwindcss.com/_next/static/media/responsive-2.8cfea49d.png) ![](https://tailwindcss.com/_next/static/media/responsive-3.e7467feb.png) ![](https://tailwindcss.com/_next/static/media/responsive-4.8e943ba2.png) ![](https://tailwindcss.com/_next/static/media/responsive-5.660185c2.png)

Filters

What’s a website these days without a few backdrop blurs? Keep stacking filters until your designer asks you to please, please stop.

blur-sm

brightness-150

grayscale

contrast-150

saturate-200

sepia

![](https://tailwindcss.com/_next/static/media/filters.debd0951.png)

Dark mode

If you’re not a fan of burning your retinas, just stick `dark:` in front of any color to apply it in dark mode.

![](https://tailwindcss.com/_next/static/media/dark-mode.light.288405b1.png) ![](https://tailwindcss.com/_next/static/media/dark-mode.dark.7219ba2e.png)

CSS variables

Customizing your theme is as simple as creating a few CSS variables.

```
@theme {
  --font-sans: "Inter", sans-serif;
  --font-mono: "IBM Plex Mono", monospace;

  --text-tiny: 0.625rem;
  --text-tiny--line-height: 1.5rem;

  --color-mint-100: oklch(0.97 0.15 145);
  --color-mint-200: oklch(0.92 0.18 145);
  --color-mint-300: oklch(0.85 0.22 145);
  --color-mint-400: oklch(0.78 0.25 145);
  --color-mint-500: oklch(0.7 0.28 145);
  --color-mint-600: oklch(0.63 0.3 145);
  --color-mint-700: oklch(0.56 0.32 145);
  --color-mint-800: oklch(0.48 0.35 145);
  --color-mint-900: oklch(0.4 0.37 145);
  --color-mint-950: oklch(0.3 0.4 145);
}
```

P3 colors

The color palette now uses more vibrant wide gamut colors without you needing to understand what any of that even means.

red

orange

amber

yellow

lime

green

emerald

teal

cyan

sky

blue

indigo

violet

purple

fuchsia

pink

rose

950

900

800

700

600

500

400

300

200

100

50

CSS grid layout

Using grid utilities directly in your HTML makes it so much easier to reason about complex layouts.

### Browse properties

![](https://tailwindcss.com/_next/static/media/css-grid-1.d6b88d05.png) ![](https://tailwindcss.com/_next/static/media/css-grid-1.mobile.d0afc6a2.png)

Treehouses

![](https://tailwindcss.com/_next/static/media/css-grid-2.d645692f.png)

Mansions

![](https://tailwindcss.com/_next/static/media/css-grid-3.45c4c3d5.png)

Lakefront cottages

![](https://tailwindcss.com/_next/static/media/css-grid-4.308d73d9.png)

Designer homes

Transitions and animations

Transitions that work the way you'd expect — throw a few utilities on an element and you're in business.

linear

ease-out

ease-in-out

ease-in

Cascade layers

Tailwind uses CSS layers so you don’t have to worry about specificity issues.

```
@layer theme, base, components, utilities;

@layer theme {
  :root {
    /* Your theme variables */
  }
}

@layer base {
  /* Preflight styles */
}

@layer components {
  /* Your custom components */
}

@layer utilities {
  /* Your utility classes */
}
```

Logical properties

Supporting multiple language text directions is no longer a nightmare.

ltr

rtl

Container queries

Tag an element as a container to let children adapt to changes in its size.

```
<div class="@container">
  <div class="grid grid-cols-1 @sm:grid-cols-2">
    <img
      src="/img/photo-1.jpg"
      class="aspect-square @sm:aspect-3/2 object-cover"
    />
    <img
      src="/img/photo-2.jpg"
      class="aspect-square @sm:aspect-3/2 object-cover"
    />
    <img
      src="/img/photo-3.jpg"
      class="aspect-square @sm:aspect-3/2 object-cover"
    />
    <img
      src="/img/photo-4.jpg"
      class="aspect-square @sm:aspect-3/2 object-cover"
    />
  </div>
</div>
```

Gradients

No need to remember that complicated gradient syntax — create silky-smooth gradients with just a few utility classes.

Power Meets Precision

### Redefining real-time performance

Our next-generation rendering engine delivers unmatched speed and efficiency, empowering creators to push boundaries like never before.

Render time performance

6.4x

Real-time frame rate

4.2x

Multi-platform build time

2.7x

3D transforms

Sometimes two dimensions aren’t enough. Scale, rotate, and translate any element in 3D space to add a touch of depth.

![](https://tailwindcss.com/_next/static/media/3d-transforms.ebde7a6a.jpeg)

How it works

## Ship faster and smaller.

text-base text-gray-950

Tailwind automatically removes all unused CSS when building for production, which means your final CSS bundle is the smallest it could possibly be. In fact, most Tailwind projects ship less than 10kB of CSS to the client.

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tailwind CSS</title>
    <link rel="stylesheet" href="/build.css" />
  </head>
  <body>

  </body>
</html>
```

```
@layer utilities {
}
```

Tailwind in the wild

## Build whatever you want, without touching your CSS file.

text-base text-gray-950

Because Tailwind is so low-level, it never encourages you to design the same site twice. Some of your favorite sites are built with Tailwind, and you probably had no idea.

[![Gumroad](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fgumroad.c0cce34f.png&w=640&q=75)](https://gumroad.com/) [![Skims](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fskims.f2c24417.png&w=640&q=75)](https://skims.com/) [![Reddit](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Freddit.407699f3.png&w=640&q=75)](https://reddit.com/)

[![Poolside](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fpoolside.a98f917b.png&w=640&q=75)](https://poolside.ai/) [![Midjourney](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fmidjourney.99f345b9.png&w=640&q=75)](https://midjourney.com/) [![NASA](https://tailwindcss.com/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fnasa.aa60f22d.png&w=640&q=75)](https://nasa.gov/)

Ready-made Components

## Move even faster with Tailwind Plus.

Tailwind Plus is a collection of beautiful, fully responsive UI components, designed and developed by us, the creators of Tailwind CSS. It's got hundreds of ready-to-use examples to choose from, and is guaranteed to help you find the perfect starting point for what you want to build.

[Explore Tailwind Plus](https://tailwindcss.com/plus?ref=home)