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
I picked up alot about SVGs in this challenge as I had issues with my SVGs not loading on live url but displays fine on localHost. I spent a whole day on this issue.

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
.toggleBtn[aria-expanded='true']::after{
    position: relative;
    height: 2rem;
    width: 2rem;
    border-radius: 100%;
    content: url('data:image/svg+xml;base64, PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMCIgaGVpZ2h0PSIzMSIgZmlsbD0ibm9uZSIgdmlld0JveD0iMCAwIDMwIDMxIj48cGF0aCBmaWxsPSIjMzAxNTM0IiBkPSJNMTUgMy4zMTNBMTIuMTg3IDEyLjE4NyAwIDEgMCAyNy4xODggMTUuNSAxMi4yIDEyLjIgMCAwIDAgMTUgMy4zMTJabTQuNjg4IDEzLjEyNGgtOS4zNzVhLjkzOC45MzggMCAwIDEgMC0xLjg3NWg5LjM3NGEuOTM4LjkzOCAwIDAgMSAwIDEuODc2WiIvPjwvc3ZnPg==');
    right: 4.5%;
    pointer-events: auto;
    align-self: center;
}

.toggleBtn[aria-expanded='false']::after{
    position: relative;
    height: 2rem;
    width: 2rem;
    border-radius: 100%;
    right: 4.5%;
    content: url('data:image/svg+xml;base64, PHN2ZyAgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iMjRweCIgaGVpZ2h0PSIyNHB4IiB2aWV3Qm94PSIwIDAgMTYgMTYiIGZpbGw9Im5vbmUiPjxnIHN0cm9rZS13aWR0aD0iMCI+PC9nPjxnIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCI+PC9nPjxnPjxwYXRoIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNNyA3SDVDNC40NDc3MiA3IDQgNy40NDc3IDQgOEM0IDguNTUyMyA0LjQ0NzcyIDkgNSA5SDdWMTFDNyAxMS41NTIzIDcuNDQ3NyAxMiA4IDEyQzguNTUyMyAxMiA5IDExLjU1MjMgOSAxMVY5SDExQzExLjU1MjMgOSAxMiA4LjU1MjMgMTIgOEMxMiA3LjQ0NzcgMTEuNTUyMyA3IDExIDdIOVY1QzkgNC40NDc3MiA4LjU1MjMgNCA4IDRDNy40NDc3IDQgNyA0LjQ0NzcyIDcgNVY3ek04IDE2QzMuNTgxNzIgMTYgMCAxMi40MTgzIDAgOEMwIDMuNTgxNzIgMy41ODE3MiAwIDggMEMxMi40MTgzIDAgMTYgMy41ODE3MiAxNiA4QzE2IDEyLjQxODMgMTIuNDE4MyAxNiA4IDE2eiIgZmlsbD0iI0FFMjNFRiI+PC9wYXRoPjwvZz48L3N2Zz4=');
    pointer-events: auto;
    align-self: center;
    top: 4px;
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
