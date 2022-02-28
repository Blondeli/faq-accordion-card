# Frontend Mentor - FAQ accordion card solution

This is a solution to the [FAQ accordion card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/faq-accordion-card-XlyjD0Oam). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

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

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See hover states for all interactive elements on the page
- Hide/Show the answer to a question when the question is clicked

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it.

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library
- [Next.js](https://nextjs.org/) - React framework
- [Styled Components](https://styled-components.com/) - For styles

**Note: These are just examples. Delete this note and replace the list above with your own choices**

### What I learned

- Making an accordion using only CSS

It uses the following HTML structure:

```html
<input type="checkbox" id="title1" />
<label for="title1">Accordion One</label>

<div class="content">
  <p>Your content goes here.</p>
</div>
```

It's important to make sure that you enter the same value for "id" (input element) and "for" (label element)!

</br>

Now we have to style the elements accordingly. First, we have to hide the "input" tag because we won't need it to show.

```css
input {
  display: none;
}
```

Now, you can style the label and the div tag according to your design. Finally, you have to add the pseudo class to show and hide the content.

```css
input + label + .content {
  display: none;
}

input:checked + label + .content {
  display: block;
}
```

</br>

- Adding arrows to the accordion

I added arrows next to each accordion label. I wanted the arrow to point down if the accordion is closed and to point up if the accordion is open. I used the pseudo class "::after" to achieve this.

```css
label {
  position: relative;
}

label::after {
  content: url(images/icon-arrow-down.svg);
  position: absolute;
  right: 15px;
  top: 15px;
}

input:checked + label::after {
  transform: rotate(180deg);
}
```

I inserted the arrow svg using the pseudo "::after" and rotated it 180 degrees when the accordion is open.

</br>

- Adding an animation to the accordion

I decided to add an animation to the accordion to have a smooth transition when opening it. I found out that I can't use the display property to hide and show my content because the animation won't work with display. Therefore, I adjusted my CSS accordingly.

```css
input + label + .content {
  height: 0;
  opacity: 0;
  overflow: hidden;
  transition: all 200ms ease-in-out;
}

input:checked + label + .content {
  opacity: 1;
  height: auto;
}
```

### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

**Note: Delete this note and the content within this section and replace with your own plans for continued development.**

### Useful resources

- [Make a pure CSS accordion without JavaScript](https://supfort.com/pure-css-accordion-without-javascript) - This helped me to create the accordion using only CSS.
- [Adding toggle plus and minus signs to a pure CSS accordion](https://supfort.com/add-toggle-plus-minus-css-accordion) - This helped me to add the arrows to my accordion.
- [WS3 Schools - Collapsibles / Accordion](https://www.w3schools.com/howto/howto_js_accordion.asp) - This page helped me to understand how I can create a smooth animation on my accordion.

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)

**Note: Delete this note and add/remove/edit lines above based on what links you'd like to share.**
