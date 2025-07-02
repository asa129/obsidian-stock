---
title: Link | Remix
source: https://remix.run/docs/en/main/components/link
author:
  - "[[@remix_run]]"
published: 
created: 2025-07-01
description: 
tags:
  - clippings
  - Remix
  - "#Link"
---
React Router v7 has been released.[View the docs](https://reactrouter.com/home)

Link

On this page

- [Props](https://remix.run/docs/en/main/components/link#props)
- [`to: string`](https://remix.run/docs/en/main/components/link#to-string)
- [`to: Partial<Path>`](https://remix.run/docs/en/main/components/link#to-partialpath)
- [`discover`](https://remix.run/docs/en/main/components/link#discover)
- [`prefetch`](https://remix.run/docs/en/main/components/link#prefetch)
- [`preventScrollReset`](https://remix.run/docs/en/main/components/link#preventscrollreset)
- [`relative`](https://remix.run/docs/en/main/components/link#relative)
- [`reloadDocument`](https://remix.run/docs/en/main/components/link#reloaddocument)
- [`replace`](https://remix.run/docs/en/main/components/link#replace)
- [`state`](https://remix.run/docs/en/main/components/link#state)
- [`viewTransition`](https://remix.run/docs/en/main/components/link#viewtransition)

## <Link>

A `<a href>` wrapper to enable navigation with client-side routing.

```tsx
import { Link } from "@remix-run/react";

<Link to="/dashboard">Dashboard</Link>;
```

Please see the [Splat Paths](https://remix.run/docs/en/main/hooks/use-resolved-path#splat-paths) section on the `useResolvedPath` docs for a note on the behavior of the `future.v3_relativeSplatPath` future flag for relative `<Link to>` behavior within splat routes

## Props

### to: string

The most basic usage takes an `href` string:

```tsx
<Link to="/some/path" />
```

### to: Partial<Path>

You can also pass a `Partial<Path>` value:

```tsx
<Link

  to={{

    pathname: "/some/path",

    search: "?query=string",

    hash: "#hash",

  }}

/>
```

### discover

Defines the route discovery behavior when using [`future.v3_lazyRouteDiscovery`](https://remix.run/docs/en/main/guides/lazy-route-discovery).

```tsx
<>

  <Link /> {/* defaults to "render" */}

  <Link discover="none" />

</>
```

- **render** — default, discover the route when the link renders
- **none** — don't eagerly discover, only discover if the link is clicked

### prefetch

Defines the data and module prefetching behavior for the link.

```tsx
<>

  <Link /> {/* defaults to "none" */}

  <Link prefetch="none" />

  <Link prefetch="intent" />

  <Link prefetch="render" />

  <Link prefetch="viewport" />

</>
```

- **none** — default, no prefetching
- **intent** — prefetches when the user hovers or focuses the link
- **render** — prefetches when the link renders
- **viewport** — prefetches when the link is in the viewport, very useful for mobile

Prefetching is done with HTML `<link rel="prefetch">` tags. They are inserted after the link.

Because of this, if you are using `nav :last-child` you will need to use `nav :last-of-type` so the styles don't conditionally fall off your last link (and any other similar selectors).

### preventScrollReset

If you are using [`<ScrollRestoration>`](https://remix.run/docs/en/main/components/scroll-restoration), this lets you prevent the scroll position from being reset to the top of the window when the link is clicked.

```tsx
<Link to="?tab=one" preventScrollReset />
```

This does not prevent the scroll position from being restored when the user comes back to the location with the back/forward buttons, it just prevents the reset when the user clicks the link.

Discussion

An example when you might want this behavior is a list of tabs that manipulate the url search params that aren't at the top of the page. You wouldn't want the scroll position to jump up to the top because it might scroll the toggled content out of the viewport!

```markdown
┌─────────────────────────┐
      │                         ├──┐
      │                         │  │
      │                         │  │ scrolled
      │                         │  │ out of view
      │                         │  │
      │                         │ ◄┘
    ┌─┴─────────────────────────┴─┐
    │                             ├─┐
    │                             │ │ viewport
    │   ┌─────────────────────┐   │ │
    │   │  tab   tab   tab    │   │ │
    │   ├─────────────────────┤   │ │
    │   │                     │   │ │
    │   │                     │   │ │
    │   │ content             │   │ │
    │   │                     │   │ │
    │   │                     │   │ │
    │   └─────────────────────┘   │ │
    │                             │◄┘
    └─────────────────────────────┘
```

### relative

Defines the relative path behavior for the link.

```tsx
<Link to=".." />; // default: "route"

<Link relative="route" />;

<Link relative="path" />;
```

- **route** — default, relative to the route hierarchy so `..` will remove all URL segments of the current route pattern
- **path** — relative to the path so `..` will remove one URL segment

### reloadDocument

Will use document navigation instead of client side routing when the link is clicked, the browser will handle the transition normally (as if it were an `<a href>`).

```tsx
<Link to="/logout" reloadDocument />
```

### replace

The `replace` prop will replace the current entry in the history stack instead of pushing a new one onto it.

```tsx
<Link replace />
```

```markdown
# with a history stack like this
A -> B

# normal link click pushes a new entry
A -> B -> C

# but with \`replace\`, B is replaced by C
A -> C
```

### state

Adds a persistent client side routing state to the next location.

```tsx
<Link to="/somewhere/else" state={{ some: "value" }} />
```

The location state is accessed from the `location`.

```tsx
function SomeComp() {

  const location = useLocation();

  location.state; // { some: "value" }

}
```

This state is inaccessible on the server as it is implemented on top of [`history.state`](https://developer.mozilla.org/en-US/docs/Web/API/History/state).

## viewTransition

The `viewTransition` prop enables a [View Transition](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API) for this navigation by wrapping the final state update in [`document.startViewTransition()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/startViewTransition):

```jsx
<Link to={to} viewTransition>

  Click me

</Link>
```

If you need to apply specific styles for this view transition, you will also need to leverage the [`useViewTransitionState()`](https://remix.run/docs/en/main/hooks/use-view-transition-state):

```jsx
function ImageLink(to) {

  const isTransitioning = useViewTransitionState(to);

  return (

    <Link to={to} viewTransition>

      <p

        style={{

          viewTransitionName: isTransitioning

            ? "image-title"

            : "",

        }}

      >

        Image Number {idx}

      </p>

      <img

        src={src}

        alt={\`Img ${idx}\`}

        style={{

          viewTransitionName: isTransitioning

            ? "image-expand"

            : "",

        }}

      />

    </Link>

  );

}
```

© [Shopify, Inc.](https://remix.run/)

Docs and examples licensed under [MIT](https://opensource.org/licenses/MIT)

[Edit](https://github.com/remix-run/remix/edit/main/docs/components/link.md)