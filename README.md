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

**_NOTE:_** The **`tailwind.config.js`** file is created via command on console`npx tailwind init` and there you must specify the content route that is intended to work with tailwindcss.

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
