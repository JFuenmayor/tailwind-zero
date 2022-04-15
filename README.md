Tailwind CSS is the most popular utility-first CSS framework (why framework?)

integration available with libraries and frameworks such as react, angular, laravel, vue... etc

utility-first meaning that the "rules" or design is fixed directly onto html component

.square { VS <div class="w-14 h-14 bg-yellow-900">
width: 3rem;
height: 3rem;
background-color: red;
}

called utility classes, preexistent classes,

installation and setup (base - no framework/plugin)

//terminal

yarn init
yarn add tailwindcss

//package.json

add
"scripts": {
"build": "tailwindcss -i src/style css -o public/output.css -w"
},
