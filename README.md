# Next.js 12 issues using @sebgroup/bootstrap
Example repo to show issue with Next.js 12 and [@sebgroup/bootstrap](https://www.npmjs.com/package/@sebgroup/bootstrap)

## Setup
1. Created starter Next.js 12 app from this guide: <https://nextjs.org/docs/getting-started#manual-setup>
1. Installed SEB Bootstrap: `npm i @sebgroup/bootstrap @sebgroup/react-components @sebgroup/fonts`
1. Created `/styles/styles.scss` importing @sebgroup/bootstrap and added referenced it in `/pages/_app.js`. 
1. Installed sass: `npm i sass`

Doesn't seem to matter using Next's new compiler or not in `next.config.js`

## Error
These are the errors I encounter after upgrading Next.js 11 -> 12.

`npm run dev`
```
error - ./styles/styles.scss:4:0
Module not found: Can't resolve '../node_modules/@sebgroup/bootstrap/scss/styles/data:image/svg+xml,<svg xmlns='http:/www.w3.org/2000/svg' viewBox='0 0 448 512'><path d='M400 32H48C21.49 32 0 53.49 0 80v352c0 26.51 21.49 48 48 48h352c26.51 0 48-21.49 48-48V80c0-26.51-21.49-48-48-48zm-6 400H54a6 6 0 0 1-6-6V86a6 6 0 0 1 6-6h340a6 6 0 0 1 6 6v340a6 6 0 0 1-6 6zm-54-304l-136 .145c-6.627 0-12 5.373-12 12V167.9c0 6.722 5.522 12.133 12.243 11.998l58.001-2.141L99.515 340.485c-4.686 4.686-4.686 12.284 0 16.971l23.03 23.029c4.686 4.686 12.284 4.686 16.97 0l162.729-162.729-2.141 58.001c-.136 6.721 5.275 12.242 11.998 12.242h27.755c6.628 0 12-5.373 12-12L352 140c0-6.627-5.373-12-12-12z' fill=''

Import trace for requested module:
./styles/styles.scss
./pages/_app.js
```

`npm run build`
```
info  - Creating an optimized production build .<w> [webpack.cache.PackFileCacheStrategy] Serializing big strings (276kiB) impacts deserialization performance (consider using Buffer instead and decode when needed)
<w> [webpack.cache.PackFileCacheStrategy] Serializing big strings (276kiB) impacts deserialization performance (consider using Buffer instead and decode when needed)
<w> [webpack.cache.PackFileCacheStrategy] Serializing big strings (277kiB) impacts deserialization performance (consider using Buffer instead and decode when needed)
info  - Creating an optimized production build  
Failed to compile.

./styles/styles.scss.webpack[javascript/auto]!=!./node_modules/next/dist/build/webpack/loaders/css-loader/src/index.js??ruleSet[1].rules[2].oneOf[10].use[1]!./node_modules/next/dist/build/webpack/loaders/postcss-loader/src/index.js??ruleSet[1].rules[2].oneOf[10].use[2]!./node_modules/next/dist/compiled/resolve-url-loader/index.js??ruleSet[1].rules[2].oneOf[10].use[3]!./node_modules/next/dist/compiled/sass-loader/cjs.js??ruleSet[1].rules[2].oneOf[10].use[4]!./styles/styles.scss
Module not found: Can't resolve '../node_modules/@sebgroup/bootstrap/scss/styles/data:image/svg+xml,<svg xmlns='http:/www.w3.org/2000/svg' viewBox='0 0 448 512'><path d='M400 32H48C21.49 32 0 53.49 0 80v352c0 26.51 21.49 48 48 48h352c26.51 0 48-21.49 48-48V80c0-26.51-21.49-48-48-48zm-6 400H54a6 6 0 0 1-6-6V86a6 6 0 0 1 6-6h340a6 6 0 0 1 6 6v340a6 6 0 0 1-6 6zm-54-304l-136 .145c-6.627 0-12 5.373-12 12V167.9c0 6.722 5.522 12.133 12.243 11.998l58.001-2.141L99.515 340.485c-4.686 4.686-4.686 12.284 0 16.971l23.03 23.029c4.686 4.686 12.284 4.686 16.97 0l162.729-162.729-2.141 58.001c-.136 6.721 5.275 12.242 11.998 12.242h27.755c6.628 0 12-5.373 12-12L352 140c0-6.627-5.373-12-12-12z' fill='' in 'C:\Users\adria\ws\node\nextjs-12-bootstrap-issue\styles'

Import trace for requested module:
./styles/styles.scss
./pages/_app.js
```