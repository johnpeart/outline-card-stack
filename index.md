---
layout: home
---

# How it works

## HTML markup

Create the card stack by creating a div with id `.card-stack`.

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

**Note**: the below is Sass mark-up

```
div#card-stack {

	display: inline-block;
	position: relative;
	white-space: nowrap;

	width: 100vw;
	height: 35rem;

	overflow-x: auto;
	overflow-y: hidden;

	margin: 0;
	padding: 2rem;

	&::-webkit-scrollbar {
	    display: none;
	}

	div.card-stack-card {

		position: absolute;
		display: inline-block;

	    top: 0;
	    right: 0;
	    bottom: 0;
	    left: 0;

	    -webkit-user-select: none;
	    -moz-user-select: none;
	    -ms-user-select: none;
	    user-select: none;

		width: 15rem;
		height: 22.5rem;

		vertical-align: top;
		font-size: initial;
		white-space: normal;
		transition: all 0.3s ease-out;

		padding: 1rem;
		margin: 0 0 0 2rem;

		background: $card-bg;
		color: $body-color-inverse;

		@include box-shadow-shallow;

		&:first-child {
			transform: translate(20vw, 10vh) rotate(-15deg);
			z-index: 1000 !important;
		}
		&:nth-child(2) {
			transform: translate(30vw, 7vh) rotate(-5deg);
			z-index: 2000 !important;
		}
		&:nth-child(3) {
			transform: translate(40vw, 5vh) rotate(-0);
			z-index: 3000 !important;
		}
		&:nth-child(4) {
			transform: translate(50vw, 7vh) rotate(5deg);
			z-index: 2000 !important;
		}
		&:nth-child(5) {
			transform: translate(60vw, 10vh) rotate(15deg);
			z-index: 1000 !important;
		}
		&:nth-child(n+6) {
			transform: translate(60vw, 10vh) rotate(15deg);
			z-index: 500 !important;
			visibility: hidden;
		}

		article {


			a {
				color: $link-color-inverse;
			}

			h2 {
				margin: 0 0 0.5rem 0;
			}

		}
	}

	div.card-stack-card-end {

		position: absolute;
		display: inline-block;

	    top: 0;
	    right: 0;
	    bottom: 0;
	    left: 0;

	    -webkit-user-select: none;
	    -moz-user-select: none;
	    -ms-user-select: none;
	    user-select: none;

		width: 1rem;
		height: 22.5rem;

		vertical-align: top;
		font-size: initial;
		white-space: normal;
		transition: all 0.3s ease-out;

		padding: 1rem;
		margin: 0 0 0 0rem;

		background: $card-bg;
		color: $body-color-inverse;

		transform: translate(60vw, 10vh) rotate(15deg);
		z-index: 1000 !important;
		visibility: hidden;

	}

	&:hover {
		div.card-stack-card {
			&:first-child {
				transform: translate(0, 10vh);
				z-index: 1000 !important;
			}
			&:nth-child(2) {
				transform: translate(20vw,10vh);
				z-index: 2000 !important;
			}
			&:nth-child(3) {
				transform: translate(40vw, 10vh);
				z-index: 3000 !important;
			}
			&:nth-child(4) {
				transform: translate(60vw, 10vh);
				z-index: 2000 !important;
			}
			&:nth-child(5) {
				transform: translate(80vw, 10vh);
				z-index: 1000 !important;
			}
			&:nth-child(n+6) {
				visibility: visible;
				transform: translate(100vw, 10vh);
				z-index: 500 !important;
			}
		}
		div.card-stack-card-end {

			visibility: hidden;
			transform: translate(120vw, 10vh);
			z-index: 500 !important;

		}
	}
}
```
# Compatability

Tested on:
- Safari 10.0.2 for MacOS Sierra
- Chrome for MacOS Sierra and Windows 10

# Source code

You can get the original code that runs this entire demo on [Github](//github.com/johnpeart/outline-card-stack).