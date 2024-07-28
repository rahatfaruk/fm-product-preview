# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

<img src="./preview-lg.jpeg" style="max-width:500px; max-height:500px; border-radius:8px;" /> 
<img src="./preview-sm.jpeg" style="max-width:500px; max-height:500px; border-radius:8px;" /> 

### Links

- Solution URL: [github repo](https://github.com/rahatfaruk/fm-product-preview)
- Live Site URL: [live site](https://rahatfaruk.github.io/rf-word-counter)

## My process

### Built with

- Semantic HTML5 markup
- TailwindCSS
- Flexbox
- Mobile-first workflow
- React.JS

### What I learned

- To make a small height component take up the full screen, I used flexbox and set the container height to 100vh with `flex-col`. Then, I assigned `flex-1` to the card container so it takes up the remaining space, and placed the `footer` at the bottom.

```html
  <!-- app container -->
  <main className="min-h-screen flex flex-col gap-6">
    <!-- product-card -->
    <div className="flex-1">
    </div>

    <footer>
  </main>
```

- If image container's height is large but img height is small then, image doesn't stretch to full-height even if we use height-100% to the img. To solve this, I wrapped the `img` in a `<figure>` element, set the `img` height to 100% (`h-full`), and controlled its size through the `figure` element.

- I needed to use different images for small and large screens. On small screens, I hide the large image, and on large screens, I show the large image and hide the small one.

```html
  <!-- img container -->
  <figure className="h-64 md:h-full md:w-1/2">
    <img src="/product.jpg" className="w-full h-full" />
  </figure>
```

- On small screens, the image and content box stack normally (top to bottom). On medium screens and above, I used flexbox and ensured both boxes take equal width using the `md:w-1/2` class, so the image and content-box stays side by side.

```html
  <!-- product card -->
  <div className="md:flex">
    <!-- img container -->
    <figure className="h-64 md:h-full md:w-1/2">
      <img src="/product-mobile.jpg" className="md:hidden w-full h-full" alt="img" />
      <img src="/product-desktop.jpg" className="hidden md:block w-full h-full" alt="img" />
    </figure>

    <div className="p-6 md:w-1/2">
      <!-- content -->
    </div>
  </div>
```

-> new tailwind classes: `tracking-*` for letter-spacing

### Useful resources

- [tailwind cdn guide](https://tailwindcss.com/docs/installation/play-cdn) - This documentation helped me to setup tailwind quickly.


## Author

- Portfolio - [Rahat Faruk](https://rahatfaruk.vercel.app)
- Linkedin - [@rahatfaruk](https://www.linkedin.com/in/rahatfaruk)
- dev.to - [@rahatfaruk](https://dev.to/rahatfaruk/)
- Frontend Mentor - [@rahatfaruk](https://www.frontendmentor.io/profile/rahatfaruk)# fm-product-preview
