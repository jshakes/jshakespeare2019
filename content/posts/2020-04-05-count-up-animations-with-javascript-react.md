---
date: 2020-04-05 21:00:00+05:00
title: A simple count-up animation with JavaScript
slug: simple-count-up-number-animation-javascript-react
description: Animating numbers using a count-up function, implemented in vanilla JavaScript and React
---
Say you want to display a numeric value on a webpage with a count-up animation, like this:

{{< codepen id="KKpjdYv" >}}

<br>

There are a few popular libraries that will do this for you, often with lots of configurable bells and whistles. I’m always reluctant to add a dependency to my application that I could write myself in under an hour ([and you should be too](https://www.theregister.co.uk/2016/03/23/npm_left_pad_chaos/)), so I did just that.

Here’s the code in vanilla JavaScript using the DOM API ([CodePen here](https://codepen.io/jshakes/pen/KKpjdYv)):

```javascript
// How long you want the animation to take, in ms
const animationDuration = 2000;
// Calculate how long each ‘frame’ should last if we want to update the animation 60 times per second
const frameDuration = 1000 / 60;
// Use that to calculate how many frames we need to complete the animation
const totalFrames = Math.round( animationDuration / frameDuration );
// An ease-out function that slows the count as it progresses
const easeOutQuad = t => t * ( 2 - t );

// The animation function, which takes an Element
const animateCountUp = el => {
	let frame = 0;
	const countTo = parseInt( el.innerHTML, 10 );
	// Start the animation running 60 times per second
	const counter = setInterval( () => {
		frame++;
		// Calculate our progress as a value between 0 and 1
		// Pass that value to our easing function to get our
		// progress on a curve
		const progress = easeOutQuad( frame / totalFrames );
		// Use the progress value to calculate the current count
		const currentCount = Math.round( countTo * progress );

		// If the current count has changed, update the element
		if ( parseInt( el.innerHTML, 10 ) !== currentCount ) {
			el.innerHTML = currentCount;
		}

		// If we’ve reached our last frame, stop the animation
		if ( frame === totalFrames ) {
			clearInterval( counter );
		}
	}, frameDuration );
};

// Run the animation on all elements with a class of ‘countup’
const runAnimations = () => {
	const countupEls = document.querySelectorAll( '.countup' );
	countupEls.forEach( animateCountUp );
};

```

And as a React component (using the useEffect and useState hooks):

```javascript
import React, { useEffect, useState } from 'react';

const easeOutQuad = t => t * ( 2 - t );
const frameDuration = 1000 / 60;

const CountUpAnimation = ( { children, duration = 2000 } ) => {
	const countTo = parseInt( children, 10 );
	const [ count, setCount ] = useState( 0 );

	useEffect( () => {
		let frame = 0;
		const totalFrames = Math.round( duration / frameDuration );
		const counter = setInterval( () => {
			frame++;
			const progress = easeOutQuad( frame / totalFrames );
			setCount( countTo * progress );

			if ( frame === totalFrames ) {
				clearInterval( counter );
			}
		}, frameDuration );
	}, [] );

	return Math.floor( count );
};

// Use the component to count to 500
<CountUpAnimation>500</CountUpAnimation>

// …optionally using the duration prop
<CountUpAnimation duration={1000}>500</CountUpAnimation>
```

There are a couple of things you might want to change to suit your needs here. The first is that the examples above use an ease-out function, so that the count slows as it nears the final number. You can use any easing function (or none at all) that you like by replacing `easeOutQuad`.  Find a list of JavaScript implementations of [easing functions in this Gist](https://gist.github.com/gre/1650294), and handy visualizations for each function on [easings.net](https://easings.net).

Secondly, you may want to format the final value, e.g. by adding commas to break up large numbers, or rounding to a certain number of decimal points ([find both of these examples here](https://blog.abelotech.com/posts/number-currency-formatting-javascript/)). You can do this immediately before you return the current count value, e.g. replacing `return Math.floor(count)` with  `return myNumberFormattingFunc(count)`.

With thanks to [Rob Heaton](https://robertheaton.com/) for helping me with this solution.
