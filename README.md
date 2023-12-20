# Frontend Mentor - FAQ accordion solution

This is a solution to the [FAQ accordion challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/faq-accordion-wyfFdeBwBz). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents
- [The challenge](#the-challenge)
- [Links](#link-to-solution)
- [Useful-resources](#useful-resources)
- [What I learned](#what-i-learned)
- [Author](#author)
- [Acknowledgments](#acknowledgments)


### The challenge

Users should be able to:

- Hide/Show the answer to a question when the question is clicked
- Navigate the questions and hide/show answers using keyboard navigation alone
- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page


### Links
- Live Site URL: [netlify.com](https://ifas-faq-accordion-challenge-solution.netlify.app/)

### Built with

- Semantic HTML5 markup
- CSS

### Useful Resources
- Resource 1: [Stackoverflow](https://stackoverflow.com/questions/10768451/inline-svg-in-css) 

  I got stuck for a whole day trying to figure out why my SVGs load properfly when used as pseudo elements' content on locals server but the live URL shows nothing. This link above is saved for future usage and references. I searched everywhere. The only thing that helped was the link above. 

### What I learned

The use of element attributes to effect CSS changes. That's the reason I picked up this challenge. Yes! I will be using a lot of element attributes in my future codes

The codes below are the reasons I wanted to do this challenge and ensure I have a good grip of them:

```html
<button 
  type="button" 
  class="toggleBtn" 
  aria-controls="ans-4" 
  aria-expanded="false"
>
```
```css
.toggleBtn[aria-expanded=true]::after{
    position: absolute;
    right: 4.5%;
    content: url(/Ifas-Accordion-Solution/images/icon-minus.svg);
    pointer-events: auto;
}

.toggleBtn[aria-expanded=false]::after{
    position: absolute;
    right: 4.5%;
    content: url(/Ifas-Accordion-Solution/images/icon-plus.svg);
    pointer-events: auto;
}

.toggleBtn[aria-expanded=false]{
  margin-bottom: 2rem;
}

.toggleBtn span{
  width: 85%;
  text-align: left;
}

button[aria-expanded="true"]+.answer{
  display: block;
  max-height: 12.3rem;
}

button[aria-expanded="false"]+.answer{
  display: none;
  max-height: 0;
}
```
```js
let toggle = document.querySelectorAll('.toggleBtn')

toggle.forEach(ele => {
    ele.addEventListener('click', function(){
        let expand = ele.getAttribute('aria-expanded')
        expand === 'true' ? ele.setAttribute('aria-expanded', 'false') : ele.setAttribute('aria-expanded', 'true')

    })
})

```

## Author
- Frontend Mentor - [@ifaronti](https://www.frontendmentor.io/profile/ifaronti)

## Acknowledgments

Thanks to frontendmentor.io for this beeautiful challenge!
