# komponents
[![build status](https://img.shields.io/travis/rxsto/komponents?style=flat-square)](https://travis-ci.org/github/rxsto/komponents) [![npm version](https://img.shields.io/npm/v/@rxsto/komponents?style=flat-square)](https://www.npmjs.com/package/@rxsto/komponents) [![license](https://img.shields.io/npm/l/@rxsto/komponents?style=flat-square)](https://github.com/rxsto/komponents/blob/master/LICENSE) [![vulnerabilities](https://img.shields.io/snyk/vulnerabilities/npm/@rxsto/komponents?style=flat-square)](https://snyk.io/vuln/search?q=%40rxsto%2Fkomponents&type=npm) [![npm bundle size](https://img.shields.io/bundlephobia/min/@rxsto/komponents?style=flat-square)](https://bundlephobia.com/result?p=@rxsto/komponents) [![npm downloads](https://img.shields.io/npm/dt/@rxsto/komponents?style=flat-square)](https://www.npmjs.com/package/@rxsto/komponents) [![discord chat](https://img.shields.io/discord/698176766748917771?style=flat-square)](https://rxs.to/discord)

A collection of useful javascript web components to keep things clean

## Features

 - **Useful** and **extensive** collection of UI elements
 - **Save** lines of code and **time**
 - Initialize **multiple** events with the **same** type per **element**
 - **Commercially** usable in **closed** source projects

## Installing
Using **npm**:

    $ npm install @rxsto/komponents
Using **yarn**:

    $ yarn add @rxsto/komponents
More to come ...

## Browser Support
![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) |![Firefox](https://raw.github.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) |![Safari](https://raw.github.com/alrra/browser-logos/master/src/safari/safari_48x48.png) |![Opera](https://raw.github.com/alrra/browser-logos/master/src/opera/opera_48x48.png) |![Edge](https://raw.github.com/alrra/browser-logos/master/src/edge/edge_48x48.png) |![IE](https://raw.github.com/alrra/browser-logos/master/src/archive/internet-explorer_9-11/internet-explorer_9-11_48x48.png) |
--|--|--|--|--|--|
latest ✔ |latest ✔ |**not** tested |latest ✔ |latest ✔ |**not** tested |

## Usage
**Button**
Nuxt.js: (https://nuxtjs.org)

```html
<template>
	<div class="index">
		<button id="btn">
			Click
		</button>
		<button id="clr">
			Clear
		</button>
	</div>
</template>
```

```js
// Import class Button
import { Button } from  '@rxsto/komponents'

export default {
	// Execute code on mount
	mounted () {
		// Create new instance of Button by passing the corresponding id (btn, clr)
		this.btn = new Button('btn')
		// Add new EventListener with name 'click_red_bg', type 'click' and callback 'makeRed()'
		this.btn.add('click_red_bg', 'click', makeRed)
		// Add a second EventListener with direct function call
		this.btn.add('click_alert', 'click', event => alert('This is an alert!'))

		// Create second instance of Button
		this.clr = new Button('clr')
		// Add new EventListener with direct function call and edit the document body
		this.clr.add('click_clear_bg', 'click', (event) => {
			document.body.style.background =  'white'
		})

		// Dispatch a click event
		this.btn.dispatch(new Event('click'))

		// Remove the EventListener with the name 'click_red_bg'
		this.btn.remove('click_red_bg')
	},
	methods: {
		// Function used for callback above
		makeRed () {
			document.body.style.background = 'red'
		}
	}
}
```
More to come ...

## Author
Oskar 'rxsto' Lang <hi@rxs.to> (https://rxs.to)
