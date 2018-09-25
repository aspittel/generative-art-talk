# Introduction to Generative Art

Generative art can be an intimidating topic -- it seems like there is a lot of math involved, and art is tricky in itself! But, it doesn't have to be difficult -- you can build some really cool things without a math or art degree. This post will break down what generative art even is and how you can get started building your own generative art.

## First, what is code art?

Code art is any art that is built using code. There are endless examples on CodePen -- for example [CSS art](https://dev.to/aspittel/learning-css-through-creating-art-54c0).

## What is generative art?

Often, generative art draws inspiration from modern art, especially pop art that makes heavy use of orderly geometric patterns. However, it is a very broad and rich category of art created with code with a central characteristic: Generative art is art built with code, but, on top of that, it incorporates a self-governed or autonomous system in some way.

Amazingly, randomness is one type of autonomous system. By incorporating chance into a piece of code art, we get a different, completely unique piece of art each time you run your script, load your page, or respond to some user interaction. 

There are also more orderly autonomous systems of course, like Mandelbrot's Fractal, derived from a deceptively simple equation.

![Mandelbrot's Fractal](https://upload.wikimedia.org/wikipedia/commons/a/a7/Mandelbrot_set_image.png)

We can also integrate both approaches, blending order and chaos to taste!

In a way, the art work becomes a collaboration between the computer and the artist. Some aspects of the artwork are controlled by the coder, but not all of them. The artist controls the randomness and the order in the art.

You might say that by using an autonomous system, the artist gives up control over their art, and the computer is doing it for them. A more nuanced perspective emerges when a new creative process is considered: tweaking these systems and observing their output. The coder-artist then engages in a feedback loop where they are constantly tweaking a system to produce more desirable and often more surprising results.

This process truly embraces experimentation and happy accidents in a profound way that reshapes the role of the artist. As generative artists, we reach for tools in our tool belts, loops, control flow, specialized functions, and so forth, blending these with often unpredictable forces, to produce novel results that may very well be completely unique and unlike anything else that exists.

## Examples of Generative Art

[Kate Compton's Flowers](http://www.galaxykate.com/apps/Prototypes/LTrees/)

[Cellular Automata and the Edge of Chaos](http://math.hws.edu/eck/js/edge-of-chaos/CA.html)

<iframe height='594' scrolling='no' title='Generative art with mouse interaction' src='//codepen.io/MarcoGuglielmelli/embed/eGCDn/?height=594&theme-id=0&default-tab=result&embed-version=2'
  frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/MarcoGuglielmelli/pen/eGCDn/'>Generative
    art with mouse interaction</a> by Marco Guglielmelli (<a href='https://codepen.io/MarcoGuglielmelli'>@MarcoGuglielmelli</a>)
  on <a href='https://codepen.io'>CodePen</a>.
</iframe>


<iframe height='583' scrolling='no' title='Animated generative art in multi-colour' src='//codepen.io/philnash/embed/wmermr/?height=583&theme-id=0&default-tab=result&embed-version=2'
frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/philnash/pen/wmermr/'>Animated
  generative art in multi-colour</a> by Phil Nash (<a href='https://codepen.io/philnash'>@philnash</a>) on <a
  href='https://codepen.io'>CodePen</a>.
</iframe>

<iframe height='547' scrolling='no' title='Impressionists Blobs' src='//codepen.io/murasaki/embed/BmOzMP/?height=547&theme-id=0&default-tab=result&embed-version=2'
  frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/murasaki/pen/BmOzMP/'>Impressionists
    Blobs</a> by murasaki uma (<a href='https://codepen.io/murasaki'>@murasaki</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<iframe height='591' scrolling='no' title='Generated Tree' src='//codepen.io/mknadler/embed/JRvGOz/?height=591&theme-id=0&default-tab=result&embed-version=2'
  frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/mknadler/pen/JRvGOz/'>Generated
    Tree</a> by Miriam Nadler (<a href='https://codepen.io/mknadler'>@mknadler</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## What goes into a piece of generative art?

* **Randomness** is crucial for creating generative art. The art should be different each time you run the generation script, so randomness is usually a large part of that.

* **Algorithms** -- Implementing an algorithm visually can often generate awesome art, for example the binary tree above.

* **Geometry** -- Most generative art incorporates shapes, and the math from high school geometry class can aid in some really cool effects.

## How can you approach a generative art piece?

There are two main strategies for creating generative art, though most will fall between the two strategies. The first is to have no results in mind and see what the computer generates as you play around. The second is that you have a very finalized idea of what you want the art to look like, and the randomness only slightly changes the end result.

## Where should you start?

If you know JavaScript, [P5.js](https://p5js.org/) is an awesome place to start. Its goal is to "make coding accessible for artists, designers, educators, and beginners." It is a wrapper on the [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API), and it simplifies a lot of the math. It focuses on drawing, but you can also do sound, video, or webcam interaction with it if you are interested in those forms of art!

## A Quick Introduction to P5

First, load in the [P5 CDN](https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.7.2/p5.js). Then, in your JavaScript file, you will add two functions that will be used in pretty much ever P5 script: `setup` and `draw`. These names are necessary for P5 to call them. 

`setup` is called when the program start. You will probably create a canvas to draw on within it using the `createCanvas` function, and you may set some defaults there. It is only called once!

`draw` is called after setup, and is executed constantly until you call `noLoop`, which will stop it from running again. You can control how many times `draw` runs each second with the `frameRate` function. With generative art, I usually put `noLoop` in the `setup` function, which makes `draw` only run once instead of continuously.

[Here's a P5 starter template](https://codepen.io/aspittel/pen/EeJJBm)

Since we've talked so much about the importance of randomness for generative art, another important function in P5 is `random`. It works similarly to JavaScript's `Math.random` but you can set a range for the numbers so that you don't have to do as much math to get the number to a useful format. 

## P5 Lines

You can create a line in P5.js like this:

```js
line(startX, startY, endX, endY)
```

Then, you can randomly generate a bunch of lines and create a simple piece of generative art like this:

<iframe height='522' scrolling='no' title='p5 Lines' src='//codepen.io/aspittel/embed/VGNOeG/?height=522&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/aspittel/pen/VGNOeG/'>p5 Lines</a> by Ali Spittel (<a href='https://codepen.io/aspittel'>@aspittel</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Even really simple scripts can generate cool pieces of art!

## P5 Shapes

You can also create shapes with P5 -- like circles, triangles, and squares.

Here's an example of creating some shapes with P5:

```js
// circle
ellipse(xCoordinate, yCoordinate, width, height)

// square
rect(xCoordinate, yCoordinate, width, height)

// triangle
triangle(xCoordinate1, yCoordinate1, x2, y2, x3, y3)
```

Then, we can create some more shapes to build something more fun!

<iframe height='577' scrolling='no' title='Shapes' src='//codepen.io/aspittel/embed/mGYgWM/?height=577&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/aspittel/pen/mGYgWM/'>Shapes</a> by Ali Spittel (<a href='https://codepen.io/aspittel'>@aspittel</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## P5 Movement

We can add movement to our drawings by removing the `noLoop` function call in the `setup` function -- check this out!

<p data-height="623" data-theme-id="0" data-slug-hash="ZMNZKd" data-default-tab="result" data-user="superbuggy" data-pen-title="p5 Lines with Movement & Color" class="codepen">See the Pen <a href="https://codepen.io/superbuggy/pen/ZMNZKd/">p5 Lines with Movement & Color</a> by James (<a href="https://codepen.io/superbuggy">@superbuggy</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

## Color

You can also play with color with generative art by randomly choosing colors. You can do this mathematically through RGB values, or you can generate a color palette with your favorite color picker (we've been using [this](https://www.colorbox.io/) one).

You can set the fill color with the `color` function. It takes a bunch of different formats, like named colors, RGBAs, and hex codes. 

You can also change the color of the outline using `stroke`. You can also remove that outline using `noStroke` or make it a different width with `strokeWeight`.

## Putting it all together

Once we have all of those pieces in place, we can combine the techniques to build some really cool stuff. 

<iframe height='265' scrolling='no' title='Colored shapes' src='//codepen.io/aspittel/embed/Pdvgda/?height=265&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/aspittel/pen/Pdvgda/'>Colored shapes</a> by Ali Spittel (<a href='https://codepen.io/aspittel'>@aspittel</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>


## Another Strategy: Tweaking Tutorials

You can also generate really cool generative art by taking someone else's work and building off of it. For example, here's the result of a tutorial by [Dan Shiffman](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw):

<iframe height='555' scrolling='no' title='Smoke Version 1: Randomly Generated Smoke' src='//codepen.io/superbuggy/embed/NLmmbE/?height=291&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/superbuggy/pen/NLmmbE/'>Smoke Version 1: Randomly Generated Smoke</a> by James (<a href='https://codepen.io/superbuggy'>@superbuggy</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Here are two tweaks of it to create different effects:
<iframe height='555' scrolling='no' title='Smoke Version 3: Gapped Circles in Time' src='//codepen.io/superbuggy/embed/VGNNmW/?height=265&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/superbuggy/pen/VGNNmW/'>Smoke Version 3: Gapped Circles in Time</a> by James (<a href='https://codepen.io/superbuggy'>@superbuggy</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<iframe height='555' scrolling='no' title='Smoke Version 5: Breathing Circles in Time' src='//codepen.io/superbuggy/embed/JaVVOE/?height=265&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/superbuggy/pen/JaVVOE/'>Smoke Version 5: Breathing Circles in Time</a> by James (<a href='https://codepen.io/superbuggy'>@superbuggy</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

[Here's](https://codepen.io/collection/nMmoem/) a Codepen Collection with even more!

You can follow tutorials, fork CodePens, or Glitch projects and create something new and unique! Just make sure to give the original artist some credit too.

## Read More

* [Generative Artistry](https://generativeartistry.com/)
* [Coding Train](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw)
* [Talk by Tim Holman](https://www.youtube.com/watch?v=4Se0_w0ISYk)

## Keep in Touch

This blog post was co-written by [James Reichard](https://twitter.com/1800THEHIVE) and [Ali Spittel](https://twitter.com/ASpittel) in conjunction with a [talk we gave](https://www.alispit.tel/generative-art-talk). If you create your own art, make sure to Tweet it at us!
