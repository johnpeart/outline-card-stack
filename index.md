---
layout: home
---

# What Outline Card Stack is

Outline Card Stack is an HTML and CSS experiment inspired by the card stack elements found on [The Outline](//theoutline.com).
It's a bit hacky and isn't meant for critical or prime-time things, but it's a cool effect.

## Compatability

Tested on:

- Safari 10.0.2 for MacOS Sierra
- Chrome for MacOS Sierra and Windows 10

## Source code

You can get the original code that runs this entire demo on [Github](//github.com/johnpeart/outline-card-stack).

# How the card stack works

## HTML markup

Create the card stack by creating a div with class `.card-stack`.

```
<div class="card-stack">

</div>
```

Add cards by creating a div with class `.card-stack-card`. 5 cards create the main card stack, the rest will be hidden. On `:hover`, a 6th card is shown on the end of the stack.

```
<div class="card-stack-card">
	
	<!-- Your content goes here -->
	
</div>

```
Add a div with class `.card-stack-card-end` to create some spacing on the end of the deck on `:hover`.

```
<div class="card-stack-card-end"></div>
```

## CSS

The CSS markup for making this work is contained the `_app.scss` file of the [Github repo](//github.com/johnpeart/outline-card-stack)
