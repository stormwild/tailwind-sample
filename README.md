# Tailwind Css Sample Project

## Pre-requisites

- Git
- NodeJs
- Visual Studio Code

## Setup

Clone repository and change directory to repository folder

```
git clone git@github.com:stormwild/tailwind-sample.git
cd taildwind-sample
```

Install packages

```
npm i
```

Open the project folder in Visual Studio Code and run Live Server


## Tutorial

Make a project directory

Initialize npm

```
cd my-tailwind-project
npm init -y
```

Install required packages

```
npm i tailwindcss postcss-cli autoprefixer
```

Run the following to initialize a tailwind config file:

```
npx tailwind init
```

This creates a `tailwind.config.js` file in the project root folder with the following contents:

```js
module.exports = {
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
}
```

This file will allow you to configure tailwind for your project.

Create a postcss config file in project root, `postcss.config.js`.

```js
module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer')
  ]
}
```

Create a source css file for example in `css/tailwind.css` with the following:

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Create a build script in `package.json` with the following command:

```json
"scripts": {
    "build": "postcss css/tailwind.css -o public/css/tailwind.css"
  },
```

Run the command

```
npm run build
```

Create an `index.html` page in the public directory with the following contents:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="/css/tailwind.css">
</head>
<body>
  <h1 class="text-4xl text-center mt-20 bg-gray-100 text-blue-500">Hello world</h1>
</body>
</html>
```

Run live server with root using the public folder and view the site.