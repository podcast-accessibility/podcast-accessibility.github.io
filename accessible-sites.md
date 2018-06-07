---
layout: page
title: Accessible podcast websites
permalink: /accessible-sites/
sidebar_link: false
---

There are many points to verify when you are looking at web accessibility. This page is really only a primer. It is not intended to be an in-depth treatise on web accessibility. But it should get you started and thinking about what to look for when you are implementing accessibility for your podcast website.

* [Keyboard](#keyboard)
* [Focus visible](#focus-visible)
* [Color contrast](#color-contrast)
* [Resize text](#text-resize)
* [Images](#images)
* [Forms](#forms)
* [Headings](#headings)
* [The standards](#standards)
* [Testing tools](#testing)


## Keyboard {#keyboard}

A critical aspect of website accessibility is the ability to navigate the page, and interact with all elements via keyboard. As it happens, this is also an easy thing for you to test. Go to your site, and use your keyboard's TAB key to move forward from one interactive element to another. If you want to go back, use SHIFT+TAB. If you want to activate an element, use the SPACE or ENTER key.

You should be able to move throughout the entire page forward and back. Your cursor should not get trapped - that is, unable to go forward or backward.

Keyboard access is critical for people who, for whatever reason, can't use a mouse or trackpad. This could be sighted keyboard-only users (including switch users), screen reader users. Or people with a broken arm.

Give yourself a challenge - To without a mouse for an hour a day. Check out [#NoMouse Challenge](https://nomouse.org/) for a bit of fun, and to encourage your friends and colleagues to use their keyboard on the web.

## Focus visible {#focus-visible}

Being able to reach all elements of a site with the keyboard is super important. Just as important is that each interactive element can provide a clearly visible focus. This is important for sighted individual who rely on keyboards.

Here are 2 things you can do to provide visible focus:

* Ensure you aren't disabling the default outline via CSS. e.g. 'outline:0'
* Provide a focus style that mirrors the hover styles. e.g. For each a:hover declaration, add a:focus


## Color contrast {#color-contrast}

Have you ever tried to read a web page that used grey text on grey background on your mobile phone out in the sun? You probably could not easily read the text. Color contrast is very important for a lot of people, and not just people with disabilities. 

A lot of coders with tired eyesight from staring at a computer screen say how important good contrast is.

The color contrast between text (referred to as foreground) and background should be at least 4.5:1 for regular text. If you are looking at large (18px or bigger) font, you can reduce the contrast to 3:1. There are multiple tools out there to test color contrast ratios. I like and use [WebAIM Color Contrast Checker](http://webaim.org/resources/contrastchecker/)

## Resize text {#resize-text}

Many people with low vision increase the font size at operating system level. They need large fonts throughout the entire computer, not on a page-by-page basis. So generally they don't use browser-based font increase features (although some people sometimes use a combination of OS large fonts and browser zoom). 

Ensure your fonts can be increased without breaking out of containers, without the lines riding on top of one another, without causing horizontal scrolling.

## Images {#images}

Images are one issue we hear about a lot from an accessibility perspective. That's because they are super important. Screen readers are not able to analyse an image and describe it.

You need to provide an alt attribute (note, not alt tag. It's an attribute, not a tag!)

There are many considerations to think about for images, but in essence, ask yourself whether the image is decorative or informative.

Should you want more information about how to decide what alternative text to use, refer to the <abbr title="World Wide Web Consortion">W3C</abbr>'s [alt text decision tree](https://www.w3.org/WAI/tutorials/images/decision-tree/). 

### Decorative images

Decorative images are those that don't provide additional information. They are there for eye candy. These images should have an empty, or null alt attribute.

```alt=""```

### Informative images

Informative images are those that provide extra information not available on the page in text. This includes images of text (which you should strive to avoid anyway). These images must have alternate text. The alternate text needs to be clear and concise. Do not use filenames as alternate text.

```alt="Image description"```

## Forms {#forms}

If you provide forms on your site, such as search form or contact form, they must be accessible. This means that you are able to navigate and fill out and submit the form fields with only the keyboard. 

### Labels

It also means that a screen reader is able to programmatically determine the purpose of each field. The easiest way to do this is to use the label tag. To associate a label with an input, use the for attribute on the label, and the id attribute on the input.
	
```<label for="email">Email</label>
	<input type="text" id="email">```
	
There **are** other ways to do this, but this is simple and reliable.

### Required fields

Everyone should be able to tell which form fields are required. Typically, designers use a red asterisk, e.g. * to designate a required field. This is not sufficient for most screen reader users to know it is a required field. An asterisk is often just read as "star" by screen readers. An asterisk may also not be enough for someone with a cognitive impairment. Or someone that doesn't use the web very much.

Use the required attribute on the input field. Use the word "required" in the label.

```<label for="fname">First Name (required)</label>
	<input type="text" id="email" required>```
	
There **are** other ways to accomplish this. But this is quite straightforward.

### Error messages	

Don't just use CSS to add a red border to the fields that have errors in them. This is not helpful to screen reader users nor to folks who are color blind ([8% of men in North America](http://www.colourblindawareness.org/colour-blindness/)).

Error messages should be clear, visibly disctinct, and associated to the erroneous field. A good way to do this is to associate the error message to the field using aria-describedby

```<label for="fname">First Name (required)</label>
	<input type="text" id="email" required aria-describedby="fname-err">
	<p id="fname-err">The first name field is required and cannot be left empty.</p>```
	
Don't forget to set focus on the erroneous field after form validation.

## Headings {#headings}

Headings are intended to provide structure to your document. They are used by over [67% of screen reader users](https://webaim.org/projects/screenreadersurvey7/#finding) to find information on your page.

Start your page with a h1. On your homepage, maybe that is the site name. On subsequent pages, perhaps the page title.

Start each section with a h2. Subsection with h3.

There should be a logical structure to the heading structure. You should not skip heading levels, or miss out on heading levels. 

## The Standards {#standards}

The accessibility standard to refer to is the World Wide Web Consortium's Web Accessibility Initiative Web Content Accessibility Guidelines. Also known as W3C WAI's WCAG. Typically referred to as WCAG. 

* Current guidelines: [WCAG 2.0](https://www.w3.org/TR/WCAG20/)
* Upcoming guidelines: [WCAG 2.1](https://www.w3.org/TR/WCAG20/)

The guidelines are broken down into principles, guidelines and success criteria. There are 4 principles, worth keeping in mind. These are: Perceivable, Operable, Understandable, and Robust. To remember them, think of the word POUR.

Note that compliance with the standards will not guarantee your site will be accessible. But following WCAG should ensure accessibility for most.

And you're not expected to learn or remember all the standards. Just remember they exist and you can refer to them as you work on your site.

## Testing tools {#testing}

Testing for accessibility is somewhat out of scope for this site. But here are a couple things you can do to check

### Manual testing

Manual testing for accessibility can be tricky if you aren't experienced with it. But the first thing you should do is use your keyboard and navigate through the site. That will already give you a good idea.

### Automated testing

Automated testing is not going to catch all the accessibility errors. You can't say "I tested with this automated tester and I had no errors, therefore my site is accessible." But automated testing tools are very useful to get an overview of what's happening on your page, and to catch coding issues without having to read lines of code one at a time.

Some good accessibility testing tools include:

* [aXe](https://www.deque.com/axe/)
* [WAVE](https://wave.webaim.org/)
* [Tenon](https://tenon.io)
