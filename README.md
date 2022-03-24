# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)



## Overview
The card design itself was not too tricky. Something I saw others at my skill level have issues with is getting the hang of flexbox, and its starting to click for me, although I no doubt will need more practice.

The true challenge here was in the cards hover states, specifically the main image which requires you to first center the svg icon by using position relative & absolute. As well I learned to utilize for the first time the ::before pseudo class together with position and absolute to add on a background color with an alpha channel. After that it was a matter of applying hover states.

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](/images/FEM%20challenge%20-%20NFT%20card.png)


### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process
I began with a mobile first approach. Some flexbox was used for the portion where the svg icons need to be on either side of the card component. In this challenge the hover states were something I needed to learn, in particular the main image hover state. I needed to utilize position; relative & absolute in conjunction with the ::before pseudoclass in order to create the color overlay effect.


### Built with

- Semantic HTML5 markup
- CSS3
- Flexbox
- Mobile-first workflow


### What I learned

I learned about position: relative and absolute. I used that to center a small SVG icon to the main wrapper of the image by setting the wrapper to relative, then the SVG icon image to absolute. That then allowed me to position it using "right" and "top" to center it.

As well I learned about the pseudoclass ::before and ::after, and how they can be used together with an empty div element to create a transparent colored overlay which shows up above the image. The rest was just a matter of applying opacity and hover states appropriatly.

```html
<div class="card">
      <div class="img-wrapper">
        <img class="main-img" src="/images/image-equilibrium.jpg" alt="Image of small glass cube">
        <img class="hover-img" src="/images/icon-view.svg">
        <div class="overlay"></div>
      </div>
```
```css

.hover-img {
    position: absolute;
    right: 41%;
    top:38%;
    opacity: 0;
    transition: all 0.3s linear;
}

 .img-wrapper:hover .hover-img {
    opacity: .8;
}

.overlay::before {
    content: '';
    width: 100%;
    height: 100%;
    display: block;  
    position: absolute; 
    top: 0;
    border-radius: 10px;
    background: hsla(178, 100%, 50%, 55%);
    transition: all 0.3s linear;
    opacity: 0;
}

.img-wrapper:hover .overlay::before {
    opacity: 1;
}
```


### Continued development

I need to continue doing challenges. They really force me to develop a broader understanding of how these styles work and behave. As well it forces me to tinker around and get a feel for what works and what doesnt.


### Useful resources

Honestly no one single resource was useful here. In the context of using pseudoclasses and hover states there just wasnt anything I could find that outright helped me. What did help me was disecting other FrontEndMentor solutions and trying things for 2 days before things began to click.

## Author

- Website - [George Stawowczyk]()
- Frontend Mentor - [@Jorgus1710](https://www.frontendmentor.io/profile/Jorgus1710)


