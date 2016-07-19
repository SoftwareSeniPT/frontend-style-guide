# SofwareSeni Frontend Styleguide

## Table of Contents
1. **Tools Setup**
   - [Text Editor](#user-content-text-editor)
   - [Git / Version Control](#user-content-git--version-control)
   - [Image Editing](#user-content-image-editing)
1. [**Development Pre-Check**](#user-content-development-pre-check)
1. **Markup Guidelines**
   - [Containment](#user-content-containment)
   - [Class Naming](#user-content-class-naming)
1. **CSS**
   - [Prefixing](#user-content-prefixing)
   - [Indenting](#user-content-indenting)
   - [Unit Size](#user-content-unit-size)
   - [CSS Reset](#user-content-css-reset)
   - [Pre & Post Processor](#user-content-pre--post-processor)
1. **Javascript**
   - [Setup](#user-content-setup)
   - [Function & Variable Naming](#user-content-function--variable-naming)
1. **Responsive Web**
   - [Meta Viewport](#user-content-meta-viewport)
   - [Mobile Check](#user-content-mobile-check)
   - [Break Points](#user-content-break-points)

## Tools Setup
Always make sure that you always use the standard tool required below while working on the project. Working with standard tool on the team project will make sure the other developers spend less setup time and the code produced will be likely has the same style.

### Text Editor
We prefered to use an open source text editor with the consideration of software cost and plugin availability. At the time this style guide is being written, [Atom Text Editor](https://atom.io) is a great choice for it. And also since we have to standardize the text editor plugin, please be sure that you use it as your default text editor. 

#### Text Editor Plugin
Using plugin on the text editor will more likely speed up the development process. When it comes to text editor's plugin, our current philosophy is to choose the one that is easy to setup & use, and non-dependent, means it will not break the code when not in use. 

Here's a list of common plugins that we do use:

1. [autoprefixer](https://atom.io/packages/autoprefixer). To make sure everytime you save your CSS file, it will automatically prefixing that file for you.
2. [Emmet](https://atom.io/packages/emmet). To create markup fast.
3. [LiveStyle plugin for Atom](https://atom.io/packages/livestyle-atom). Alongside with [Emmet Live Style Chrome Extension](https://chrome.google.com/webstore/detail/emmet-livestyle/diebikgmpmeppiilkaijjbdgciafajmg?hl=en), this will be powerful tool to speed up the process of CSS editing. It will make sure everything you change on the browser will also changed on the text editor and vice versa. 
4. [atom-beautify](https://atom.io/packages/atom-beautify). Always keep your code beauty and easy to read. This plugin will automatically do it for you.

### Git / Version Control
Some projects on SoftwareSeni are using version control, but some are not. Whenever it is possible to use version control, always use it. It will save your time when bad things happen because you will always have chance to roll it back.
A simple guide to setup your git can be found [here](http://rogerdudler.github.io/git-guide)

### Image Editing
Every front-end developer on SoftwareSeni is equipped with Adobe Photoshop subscription. You don't have to have a deep knowledge on that software, but basic understanding on how to crop image and how to compress to smaller possible size is needed. If you have to work with SVG, please make sure your manager give you the Adobe Illustrator software and subscription.

## Development Pre-Check
Always make sure to check all of the list below before you start a project.
- [ ] **CSS Reset**. See [CSS Reset](#css-reset)
- [ ] **Auto-prefixing plugin**. See [Text Editor Plugin](#user-content-text-editor-plugin)
- [ ] **Base Styles**. Make sure you always include the base style for font size, line height, font color, link color, and hover link color on your stylesheet.

```css
html, body {
    height: 100%;
}
body {
    font-family: 'Lato', sans-serif;
    font-size: 14px;
    color: #3c3c3c;
    margin: 0;
    line-height: 1.5;
}
h1, h2, h3, h4, h5, h6 {
    margin: 0;
    padding: 0;
    line-height: 1;
    font-weight: 1.3;
}
img {
    max-width: 100%;
    height: auto;
}
/*
 * Links
 */

a {
    color: #506A85;
    text-decoration: none;
    outline: none;
}
a:hover {
    color: #506A85;
    text-decoration: none;
}
a img {
    border: none;
}
```
- [ ] **CSS Border Box**. Border box is needed for making grid on responsive web. So always make sure you include this on your CSS
```css
* {
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
    -webkit-text-size-adjust: none;
    -webkit-font-smoothing: antialiased;
}
*:after, *:before {
    box-sizing: border-box;
}
```
- [ ] **Viewport Meta Tag**. See [Meta Viewport](#user-content-meta-viewport) section
- [ ] **Mobile Check**. See [Mobile Check](#user-content-mobile-check) section

## Markup Guidelines
### Containment
When creating container for element, always remember to avoid these:

1. **Never create a single container for all elements**
    
    Some section could be full width/fluid, but some other could be fixed width. So the best way is to create a container inside every section. This way we can set each container to be full width or fixed width.

2. **Never set width for fixed width container**
    
    Setting width for fixed width container will brake its responsive layout. The best way is to use `max-width` instead of `width`

### Class Naming
Class names should all be lower case, with hyphens as spaces. So use `work-grid`, not `WorkGrid` or `work_grid`.

**Good:**
```css
  .block-slideshow { 
      font-size: 22px; 
      margin-top: 33px; 
  }
```

**Bad:**
```css
  .blockSlideshow { 
      font-size: 22px; 
      margin-top: 33px; 
  } 

  .block_footer { 
      background-color: #000;
  }
```
## CSS
### Prefixing
Don’t forget to always prefixing the stylesheet to avoid the cross browser issues on the future. The easiest way to do this is by installing auto-prefixer plugin on your Atom text editor. It will automatically prefixing the CSS whenever new change happen. See [Text Editor Plugin](#user-content-text-editor-plugin) section to get the link of the plugin.

### Indenting
Use soft tabs with four spaces. It will make the code easy to read.

**Good:**
```css
footer {
    text-align: center;
    padding: 20px;
    font-size: 14px;
    color: #8E8E8E;
}

footer a {
    color: #2e7e83;
}
```

**Bad:**
```css
footer {
    text-align: center;
    padding: 20px;
    font-size: 14px;
    color: #8E8E8E;
}

footer a {
    color: #2e7e83;
}
```

### Unit Size
As most of the projects on SoftwareSeni require to be pixel perfect, we encourage all front-end developer to use **px** as default unit size for almost everything like font-size, padding, margin. Do not use percent unit size on padding and margin unless you know what you are doing.

### CSS Reset
All project starter themes on SoftwareSeni have already included CSS reset on the stylesheet. The CSS reset will make your styling consistent on every major browser and will help you avoid future errors.

### Pre & Post Processor
Avoid using any preprocessors or postprocessor. We have a very minimal amount of boilerplate code to start with in our stylesheet and it allows us to keep our CSS files very slim. 

## Javascript
### Setup
To avoid any namespace issues and keep things simple, all the main logic of the site gets wrapped in one large object. The main js file on the site might look something like this in its most stripped-down form:
```js
var app = {
    init: function() {
        app.firstFunction();
        app.secondFunction();
        app.thirdFunction();
    },
    firstFunction: function(){

    },
    secondFunction: function(){

    },
    thirdFunction: function(){

    }
};
jQuery(document).ready(function($){
    app.init();
});
```

### Function & Variable Naming
Variables should be camel cased like initMenu or initVideoDetail.

**Good:**
```js
  var headerHTML = jQuery('#header').html();
```

**Bad:**
```js
  var header-HTML = jQuery('#header').html();
  var footer_visibility = false;
```

## Responsive Web
### Meta Viewport
Viewport meta tag will make sure the site will displayed at proper zoom on mobile device. Make sure you include this before the closing `</head>` tag.
```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
```
### Mobile Check
If you are working with wordpress, you can use snippet below to make wordpress add an additional class name on body when user open the page on mobile device.
```php
    // Add specific CSS class by filter
    function custom_class_names($classes) {
        global $post;
        $state = get_conditional_state($post);
        if ( $state ) {
            $classes[] = $state;
        }
    		// Mobile Detects
    		if( wp_is_mobile() ) {
    			$classes[] = 'is-mobile';
    		} else {
    			$classes[] = 'not-mobile';
    		}
        	return $classes;
        }
    add_filter('body_class','custom_class_names');
```
### Break Points
All mobile-related CSS should be included in one separate file (usually mobile.css) stylesheet within the template. The breakpoints will be somewhat specific to each site and design, but in general here is a good starting point. We have prepared a working example for you here.
```css

/* Larger that laptop */
@media (max-width: 1200px) {

}
/* This is basically a decent laptop, up to an average external display */
@media (max-width: 992px) {

}
/* Up to a tablet (includes iPads in landscape) */
@media (max-width: 768px) {

}
 /* Smaller than an iPad portrait (so all phones) */
@media (max-width: 480px) {

}
```
