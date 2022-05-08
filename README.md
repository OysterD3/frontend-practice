
# JavaScript Frontend Practice Project
This project is mainly targeting those who wants job transition to Frontend, intern, fresh graduate, junior and those who want to learn more in Frontend.

For those frontend experts, kindly contribute or help those who seek help!

Feel free to contribute more information by creating a Pull Request.

Most importantly, don't be toxic. Everyone is learning.

If you have any questions/suggestions, kindly create a post in [Discussion](https://github.com/OysterD3/frontend-practice/discussions)

## Open API
 1. [TMDB (The Movie Database)](https://developers.themoviedb.org/3)
 2. [Coingecko API](https://www.coingecko.com/en/api/documentation)
 3. Add what you know here by creating a PR!

## Rules
1. Use any framework you like ([React](https://reactjs.org/), [Svelte](https://svelte.dev/), [Vue](https://vuejs.org/), [Next](https://nextjs.org/), [Nuxt](https://nuxtjs.org/), etc)
2. Deploy to any free hosting ([Netlify](https://www.netlify.com/), [Heroku](https://www.heroku.com/), [Vercel](https://vercel.com/), etc)
3. When committing your changes, try to follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
  
## Criteria
### Level 0
1. Fully functioning UI/UX with routers

### Level 1
1. Everything in Level 0
2. Don't use any UI component library (ElementUI, AntDesign, MaterialUI, etc)
3. Able to use Tailwindcss/Windicss/Unocss/Bootstrap/etc
4. Able to filter results

### Level 2
1. Everything in Level 1
2. Don't use any high-level framework (Next, Nuxt, Sveltekit)
3. Lazy load components/routes
4. Use state management library ([Vuex](https://vuex.vuejs.org/), [Pinia](https://pinia.vuejs.org/), [Redux](https://redux.js.org/), [MobX](https://mobx.js.org/README.html), etc)
5. Google Lighthouse Accessibility & Best Practices & Performance score >= 50

   Read More:  [Tips on Improving Google Lighthouse score?](#tips-on-improving-google-lighthouse-score)
 
### Level 3
 1. Everything in Level 2
 2. Written in [TypeScript](https://www.typescriptlang.org/)
 3. Mobile Responsive/Adaptive
 4. Google Lighthouse Accessibility & Best Practices & Performance score >= 80

### Level 4
1. Everything in Level 3
2. Don't use any CSS library
3. Use CSS preprocessor ([SCSS/SASS](https://sass-lang.com/), [Less](https://lesscss.org/), [Stylus](https://stylus-lang.com/), etc)
4. Style should work across various browsers (Edge, Firefox, Chrome, Safari)
5. Without any help of library, implement infinite scroll

### Level 5
1. Everything in Level 4
2. Use [Vite](https://vitejs.dev/) as bundler
3. Without the help of the plugins, implement file system based routing. Click here for example
4. Run your dev server in port `:1234`

### Level 6
1. Everything in Level 5
2. Write Unit Test
3. Write Component Test
4. Write End-to-end Test

### Level 7
1. Everything in Level 6
2. Change your web app to PWA (Progressive Web App)
3. Implement [Workbox](https://developers.google.com/web/tools/workbox) and use any caching strategy to cache responses from API


## Examples
### File system based routing (Vite only)
You don't need to add route manually. Put your `views/` into `pages/` it will generate for you.  
   1. `/pages/foo/index.vue` will generate path `/foo`  
  2. `/pages/home/index.vue` will generate path `/` 

You must use `import.meta.glob` or `import.meta.globEager` to achieve this. Check out https://vitejs.dev/guide/features.html#glob-import

### Tips on Improving Google Lighthouse score

1. Suitable image size/resolution
   
   Do not use ridiculously large image (4000 x 3000 px), it takes up a lot of bandwidth and slows down your website. For example, you can use an image with size of 1920x1080 or 1600x900 as your hero image.
   
   > Cropping your image using image editing tool, we are not talking about `resize` property in CSS here.
   
   Some common image formats that you can use are JPG, PNG, GIF, SVG or even [WebP](https://developers.google.com/speed/webp)
   
   Read More: [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
   
2. `Development` and `Production` build
   
   Take [webpack](https://webpack.js.org/) as an example, the goals of `development` and `production` builds differ greatly. In `development`, we want strong source mapping and a localhost server with live reloading or hot module replacement. In `production`, our goals shift to a focus on minified bundles, lighter weight source maps, and optimized assets to improve load time.

3. Purge unused CSS
   
   With tool like [PurgeCSS](https://purgecss.com/), you can remove unused CSS from your project. When you are building a website, chances are that you are using a css framework like `Bootstrap`, Materializecss, Foundation, etc... But you will only use a small set of the framework and a lot of unused css styles will be included.

   This is where PurgeCSS comes into play. PurgeCSS analyzes your content and your css files. Then it matches the selectors used in your files with the one in your content files. It removes unused selectors from your css, resulting in smaller css files.

   Or, you are using a UI framework in your project such as [Material UI](https://mui.com/), how to [minimize bundle size](https://mui.com/material-ui/guides/minimizing-bundle-size/) might be a good read.

   You can do similar thing on your `js` module. [`Tree shaking`](https://webpack.js.org/guides/tree-shaking/), a term commonly used in the JavaScript context for dead-code elimination.
   
 4. Minify Resources/Use minified assets

    Take `Bootstrap` as an example, common libraries or JavaScript plugins often offer a few version of source code, including compiled and minified CSS and JS(bootstrap.min.\*). The minified CSS and JS files have smaller file size.
        
        bootstrap/
        ├── css/
        │   ├── bootstrap.css
        │   ├── bootstrap.css.map
        │   ├── bootstrap.min.css
        │   ├── bootstrap.min.css.map
        │   ├── bootstrap-grid.css
        │   ├── bootstrap-grid.css.map
        │   ├── bootstrap-grid.min.css
        │   ├── bootstrap-grid.min.css.map
        │   ├── bootstrap-reboot.css
        │   ├── bootstrap-reboot.css.map
        │   ├── bootstrap-reboot.min.css
        │   └── bootstrap-reboot.min.css.map
        └── js/
            ├── bootstrap.bundle.js
            ├── bootstrap.bundle.min.js
            ├── bootstrap.js
            └── bootstrap.min.js
