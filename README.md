# Frontend Mentor - Stats preview card component solution

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)
- [Acknowledgments](#acknowledgments)


## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Screenshots

**Mobile Preview**

![My solution to design](./design/mobile-size.jpg)

**Desktop preview** 
![My solution to design](./design/desktop-size.jpg)


### Links

- Solution URL: [Solution on FrontendMentor.io](https://www.frontendmentor.io/solutions/mobilefirst-approach-using-bem-and-css-flexbox-ZidZpy2Jv)
- Live Site URL: [Live site preview](https://smita-14.github.io/stats-preview-card-challenge/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- BEM architecture
- Flexbox
- Mobile-first workflow


### What I learned

- I learned about background-blend-mode and mix-blend-mode property. Although both of them have different use cases but in this particular challenge I had to pair both to get the desired result.

- I ran into an issue where there was a padding at the bottom of the image and i could not trace where it was coming from. I then realized that image is an inline element and the properties like line-height and font-size would affect them causing them to have bottom padding. The solution was simple which was to make it an inline-block or a block element.

- I learned that when using picture tag it is much better to apply class to img rather than picture tag itself because it is the img tag which displays the image and does all the hard work and if we apply class to picture tag, the property set might not work well.

- I found various ways to adjust image at the right spot. It was a tedious task to choose which one would give the appropriate result. Those three ways are listed below:

1. **Using div html tag and background-images property in css**

    ```html
    <div class="img"></div>
    ```
    ```css
    .img {
      height: 100%;
      width: 100%;
      background-image: url("../image/mobile-image.jpg");
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
    }
    ```

2. **Using picture tag in html** 

    ```html
    <picture>
      <source media="(max-width: 1079px)" srcset="../image/mobile-image.jpg">
      <img class="img" src="../image/desktop-image.jpg" alt="meeting">
    </picture>
    ```

3. **Using multiple img tag in html and display property in css**

    ```html
    <img class="mobile-img" src="../image/mobile-image.jpg" alt="meeting">
    <img class="desktop-img" src="../image/desktop-image.jpg" alt="meeting">
    ``` 

    ```css
    /*when the screen size is of mobile set the display property of desktop-img to none and vice versa*/
    .desktop-img {
      display: none;
    }
    ```

    In my case using picture element was a better option as it works well when you have multiple images saving us from writing separate media queries.

### Continued development

This challenge helped me exercise on beginner level of flexbox and now I would like to brush my skills on intermediate level. Also height property can be tricky sometimes and I look forward to work on it till I am comfortable with it.


## Author

- Frontend Mentor - [@Smita-14](https://www.frontendmentor.io/profile/Smita-14)



## Acknowledgments

A big thanks to [MRZ.Code.Manufacture for this youtube tutorial](https://www.youtube.com/watch?v=zaHdmJf_ld4) that helped me understand how to match color overlay on the image, [this video by Kevin Powell](https://www.youtube.com/watch?v=Rik3gHT24AM) where he explained picture element and [this question answered on StackOverflow.](https://stackoverflow.com/questions/17771230/img-has-5px-extra-padding-at-bottom-of-div/17771249#17771249)
