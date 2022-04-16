# Tailwind CSS Zero

Tailwind CSS is the most popular utility-first CSS framework (why framework?)

integration available with libraries and frameworks such as react, angular, laravel, vue... etc

utility-first meaning that the "rules" or design is fixed directly onto html component

| Utility-First (API style)                | Traditional Css                                               |
| ---------------------------------------- | ------------------------------------------------------------- |
| ` <div class="w-14 h-14 bg-yellow-900">` | `.square { width: 3rem; height: 3rem background-color:red; }` |

called utility classes, preexistent classes,

## Installation and setup (base - no framework/plugin)

(Why not CDN? Because is not customizable, not directives, not third-party, not sgc)

#### **`terminal`**

```bash
yarn init
yarn add tailwindcss
```

#### **`package.json`**

```js
"scripts": {
    "build": "npx tailwindcss -i src/styles.css -o public/output.css -w"
},
```

Create the following file where all the styles will be used

### **`src/styles.css`**

<br/>

> **_Important:_** The **`tailwind.config.js`** file is created via command on console`npx tailwind init` and there you must specify the content route that is intended to work with tailwindcss.

<br/>

## Utilities

on the styles file can be imported one or muiltiple utility clases/directives such

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

while on html file is added the output styles and is ready to use API-Style tailwind

### **`index.html`**

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    //Add output stylesheet
    <link rel="stylesheet" href="./output.css" />
    <title>TailwindCss microcourse</title>
  </head>
  <body>
    //Use of tailwind api/syntax on class attribute of elements
    <div class="container bg-indigo-50 mx-auto">
      <p class="text-3xl font-bold">Hello world!</p>
    </div>
  </body>
</html>
```

<br/>

## Breakpoints

The key element to take into account is the flag before any tailwind element called out

| Breakpoint   | Properties           |
| ------------ | -------------------- |
| none         | width: 100%;         |
| sm (640px)   | `max-width: 640px;`  |
| md (768px)   | `max-width: 768px;`  |
| lg (1024px)  | `max-width: 1024px;` |
| xl (1280px)  | `max-width: 1280px;` |
| 2xl (1536px) | `max-width: 1536px;` |

```html
<div class="lg:container">Hi! i'm a container!</div>
```

> **_Note:_** The use of the prefix lg in this case means: _*If the viewport is 1280px or more, the following tailwind element will be applied*_

As any other element from tailwindcss, containers are stated as default attributes [Tailwind Documentation](https://tailwindcss.com/docs/container).

## Flex & Grid

To make use of flex is appliable the class `flex`, and same logic applies with `grid`

### Cheatsheet

`gap` : Space between cols (applies both flex and grid)

`flex-col` | `flex-row` | `flex-col-reverse` | `flex-row-reverse` : Flex direction

`flex-wrap` | `flex-wrap-reverse` | `flex-nowrap` : Flex wrap

`flex-initial` | `flex-1` : Flex size behavour

`grid-cols-n` : Number of colums per row

`col-span-n` : Size of cols used by grid child

`col-start-n` | `col-end-n` : start and/or end at the nth grid lin

> **_NOTE_** CSS grid lines start at 1, not 0, so a full-width element in a 6-column grid would start at line 1 and end at line 7.

## Utility-first API

Applying pre-existing classes can be tedious to maintain and scalate among large applications, that is why is created the `@apply` directive as:

### **`styles.css`**

```css
.btn {
  @apply py-2 px-4 font-semibold;
}
.btn-green {
  @apply rounded-lg shadow-md text-white bg-green-500 hover:bg-green-700;
}
```

### **`index.html`**

```html
<button
  class="py-2 px-4 font-semibold rounded-lg shadow-md text-white bg-green-500 hover:bg-green-700"
>
  Click me!
</button>
<button class="btn btn-green">Click me!</button>
```

And both scenarios will render the same css content
