## Website Performance Optimization portfolio project

The project creates a portfolio site using Cameron Pittman's data. It also includes a web app,
Cam's Pizzeria, thats you order a pizza with random ingredients.

To run the site:
1 go to https://jackieli311.github.io/jackieli311/mobile-portfolio
2 run the index.html file.

To view Cam's Pizzeria, click the Cam's Pizzeria link. Select a pizza (Pick a Pizza Now button) and/or pizza size (slider).



Changes made to optimize the site:


#### Part 1: Optimize PageSpeed Insights score for index.html

Initial Pagespeed score is about 30% on mobile and desktop

Made the following changes to idex.html:

1. Set analytics.js to run asynchronously

2. Set media query for print style sheet

3. Removed the 700 size fonts.

4. Optimized sizes for profilepic.jpg, pizza.png, pizzeria.jpg

5. Moved the content of style.css to "inline" to speed loading of the initial page.

Follow-up checks on the Pagespeed score indicate the largest gain from 4) Optimized images and 5) inlining the styles.css.




#### Part 2: Optimize frame rate for views/pizza.html

I made the following changes to views/js/main.js:

1. In the function (document.addEventListener('DOMContentLoaded', function() ) that generates the sliding pizza, I changed the   maximum value of i in the for loop from 200 to 20, as that seemed a sufficient numeber of sliding pizzas to be displayed on any one frame. This reduced the load time by making the function more efficient.

2. In function updatePositions():
  Changed querySelectorAll to getElementsByClassName as it is more efficient (has fewer elements to search).

3. In function changePizzaSizes(size):

    - Moved the getElements (pizzaContainers) into a variable outside of the loop so it does both need to be processed for each element re-size.

    - Changed querySelectorAll to getElementsByClassName as it is more efficient (has fewer elements to search).

    - These two changes take the re-size time from about 100ms to less than .50 ms, as shown in the JS console in Chrome.

 After changes, I measure the following (in Chrome Canary):

  - Average time to generate last 10 frames: from .0234 to .033
  - Time to resize pizzas: .224


