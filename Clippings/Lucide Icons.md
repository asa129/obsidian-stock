---
title: "Lucide Icons"
source: "https://lucide.dev/guide/packages/lucide-react"
author:
  - "[[Lucide]]"
published:
created: 2025-06-11
description: "Beautiful & consistent icon toolkit made by the community."
tags:
  - "clippings"
---
## Lucide React

Implementation of the lucide icon library for react applications

## Installation

## How to use

Lucide is built with ES Modules, so it's completely tree-shakable.

Each icon can be imported as a React component, which renders an inline SVG element. This way, only the icons that are imported into your project are included in the final bundle. The rest of the icons are tree-shaken away.

### Example

Additional props can be passed to adjust the icon:

## Props

| name | type | default |
| --- | --- | --- |
| `size` | *number* | 24 |
| `color` | *string* | currentColor |
| `strokeWidth` | *number* | 2 |
| `absoluteStrokeWidth` | *boolean* | false |

### Applying props

To customize the appearance of an icon, you can pass custom properties as props directly to the component. The component accepts all SVG attributes as props, which allows flexible styling of the SVG elements. See the list of SVG Presentation Attributes on [MDN](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/Presentation).

## With Lucide lab or custom icons

[Lucide lab](https://github.com/lucide-icons/lucide-lab) is a collection of icons that are not part of the Lucide main library.

They can be used by using the `Icon` component. All props like regular lucide icons can be passed to adjust the icon appearance.

### Using the Icon component

This creates a single icon based on the iconNode passed and renders a Lucide icon component.

## Dynamic Icon Component

It is possible to create one generic icon component to load icons, but it is not recommended. Since it is importing all icons during build. This increases build time and the different modules it will create.

`DynamicIcon` is useful for applications that want to show icons dynamically by icon name. For example, when using a content management system with where icon names are stored in a database.

For static use cases, it is recommended to import the icons directly.

The same props can be passed to adjust the icon appearance. The `name` prop is required to load the correct icon.