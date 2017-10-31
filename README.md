# Udacity Website Optimisation Project 

This project required improving the performance of loading and rendering an existing portfolio site. The speed of the site was measured using Chrome dev tools to identify performance bottlenecks, and then optimizations were applied to address those bottlenecks.

## Usage:

The project I had been working on is hosted on GitHubPages. So you can directly visit the below URL and carry out all the page speed tests 

URL1 : <https://sohampatel12.github.io/frontend-website-optimisation/>
URL2 : <https://sohampatel12.github.io/frontend-website-optimisation/views/pizza.html>


## Optimisations of index.html: To get Page Speed Insights score above 90
- Compressed image files taking up long times to load. 
- Inlined CSS 
- Added async attribute to google analytics javascript.
- Optimised google fonts.



## Optimizations of views/js/main.js for pizza.html: To get 60fps working and faster pizza size changes


- Modfied the changePizzaSizes function to select randomPizzaContainer elements by class name (rather than querySelectorAll) and add them to a pizzaElements array.
- Moved the computation of the dx and newwidth variables outside of the for loop as it doesn't seem necesary to recompute them on each pass through that loop.
- Modified the updatePositions function to select the mover elements by class name.
- Since there are only 5 unique phases of the moving pizzas, I moved the phase calculation into its own for loop that appends each phase to an array called phaseList, rather than declaring and setting the phase variable each time.
- The pizza item styles are changed by accessing the relevant element of the phaseList array as it loops through each element in the items array.
- Moved the declaration of the pizzaDivs variable outside of the for loop, since it is only necessary to make one DOM call there.
- Changed the number of pizzas generated on page load to be based on the browser window resolution.
- Changed the querySelector call for selecting movingPizzas1 element to getElementById, saved it to a local variable called movingPizzas, moved it outside of the for loop, and referenced the movingPizzas variable inside the loop.
## Optimizations to views/css/style.css

- Added backface-visibility: hidden; to the .mover class, to move each animated pizza to its own composite layer.
## Browser Support

![IE](https://raw.github.com/alrra/browser-logos/master/internet-explorer/internet-explorer_48x48.png) | ![Chrome](https://raw.github.com/alrra/browser-logos/master/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/alrra/browser-logos/master/firefox/firefox_48x48.png) | ![Opera](https://raw.github.com/alrra/browser-logos/master/opera/opera_48x48.png) | ![Safari](https://raw.github.com/alrra/browser-logos/master/safari/safari_48x48.png)
--- | --- | --- | --- | --- |
IE 9+ ✔ | Latest ✔ | Latest ✔ | Latest ✔ | Latest ✔ |

## License

MIT License

Copyright (c) 2017 Soham Patel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
