- [References](#references)
- [Instruction](#instruction)
- [✅ 2W1H](#-2w1h)
  - [Q1. What does it mean by `-y` flag?](#q1-what-does-it-mean-by--y-flag)
  - [Q2-1. Why do I need to install `webpack-cli` as well?](#q2-1-why-do-i-need-to-install-webpack-cli-as-well)
  - [Q2-2. What is the shorthand expression for `--save-dev`?](#q2-2-what-is-the-shorthand-expression-for---save-dev)
  - [Q3. How do you excute your custom build script?](#q3-how-do-you-excute-your-custom-build-script)
  - [Q4. Why do you use `require statement` in `webpack.config.js` instead of `import`?](#q4-why-do-you-use-require-statement-in-webpackconfigjs-instead-of-import)

# References

* [why do we need to install webpack-cli](https://webpack.js.org/guides/installation/)
* [why do we use require statement in webpack.config.js](https://jeonghwan-kim.github.io/series/2019/12/10/frontend-dev-env-webpack-basic.html)

# Instruction

Go into `index.html` and complete `TODO: 웹팩으로 빌드한 자바스크립트를 여기에 로딩하세요`.

1. Start project by `npm init -y`
2. Install webpack pacakge by `npm i --save-dev webpack webpack-cli`
3. Add npm script in `package.json` like below:

```json
"scripts: {
    "build": "webpack"
}
```

4. Create webpack config file named `webpack.config.js` like below:

```js
const path = require('path);

module.exports = {
    mode: 'development',
    entry: {
        main: 'src/app.js'
    },
    output: {
        filename: '[name].js',
        path: path.resolve('./dist')
    }
}
```

5. Run build command by `npm run build`
6. Eject output script to `index.html` by `<script src="./dist/main.js"></script>`
7. Check out `index.html` using one of the ways you like:

* `open index.html`
* `Open with Live Server`: 
* `npx lite-server`

# ✅ 2W1H

## Q1. What does it mean by `-y` flag?

It means you use all the default options by saying yes.

## Q2-1. Why do I need to install `webpack-cli` as well?

According to [the official documentation](https://webpack.js.org/guides/installation/), you need to install it if you're using webpack v4 or later.

## Q2-2. What is the shorthand expression for `--save-dev`?

`-D`. Therefore, you can use `npm i -D webpack webpack-cli` instead.

## Q3. How do you excute your custom build script?

`npm run build`

## Q4. Why do you use `require statement` in `webpack.config.js` instead of `import`?

Because we're writing in nodejs context where you use CommonJS module system. On the other hand, `import` is a keyword introduced in ES6(ES2015). That's why we also use `module.exports = {}` instead of `export default`.

