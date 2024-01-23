# Part 3 - Interaction (Output)

We have briefly seen ***input*** interaction by making a button "clickable"

**HTML** ([index.html](#index.html))
```HTML
<!-- Load a script -->
<script src="script.js" defer></script>

<!-- Give the element a unique ID -->
<button id="my_btn">Click Me</button>
```
**JavaScript** ([script.js](#script.js))
```JS
// Add an event listener to the button
document.getElementById("my_btn").addEventListener("click", my_func);

// Create a function for the listener to call
function my_func(event) {
  console.log("I was clicked!");
  // Do some work
}
```

Now there are two questions:
1. What is the "some work"?
2. How do we give ***output***? (TL;DR - [click here](https://www.w3schools.com/js/js_htmldom_html.asp))

The work will depend on the program and the developer. What are you trying to accomplish? In our `New Game` button, we are collecting the names of the users.
```JS
let p1_name = "";
let p2_name = "";

function new_game() {
  let answer = confirm("Are you sure you want a new game?");

  // The confirm dialog returns `true` or `false`
  if (answer) {
    p1_name = prompt("Player 1 (X) - What is your name?");
    p2_name = prompt("Player 2 (O) - What is your name?");
  }
}
```

Notice how the `p1_name` and `p2_name` variables are declared outside any functions? These are called _global variables_ and are available throughout the entire program. But currently, those names do not get displayed and nothing else happens.

### Displaying the user names and the turn indicator

In the code above, we collected the user names into `p1_name` and `p2_name`. We will also need a variable to keep track of whose turn it is:
```JS
'use strict';
// Global variables
let p1_name = "";
let p2_name = "";
let turn = 1;   // Default to player 1's turn first (X's)
```

In order to display the user names in our scoring summary, we need to give the output locations in the HTML **unique identifiers**. This will depend on how you set yours up, but here is an example:
```HTML
<!-- Turn indicator (could be a <p> or anything) -->
<div id="turn_indicator"></div>

<!-- Scoring Table -->
<table border="1">
  <tr>
    <td id="p1_heading"></td>
    <td id="p2_heading"></td>    
  </tr>
  <tr>
    <td id="p1_score"></td>
    <td id="p2_score"></td>
  </tr>
</table>
```

The question is - **How do we modify the _contents_ of those elements?**

#### [innerHTML](https://www.w3schools.com/jsref/prop_html_innerhtml.asp) vs [innerText](https://www.w3schools.com/jsref/prop_node_innertext.asp)
Page elements have two String _attributes_ we can modify using JavaScript. One allows us to create/insert actual _HTML_ ([innerHTML](https://www.w3schools.com/jsref/prop_html_innerhtml.asp)) inside a tag and the other is strictly to insert or modify the _text_ ([innerText](https://www.w3schools.com/jsref/prop_node_innertext.asp)) displayed by a tag.

Let's start by setting up whose turn it is:
```JS
function new_game() {
  ...

  // Start the game with Player 1 (X)
  turn = 1;
  display_turn();
}

// A function to update the turn indicator
function display_turn() {
  // Let's grab the turn indicator HTML Element
  let output = document.getElementById("turn_indicator");

  // Decide whose turn it is using the 'turn' global variable
  if (turn == 1) 
    output.innerText = "Player 1 (X)";
  else
    output.innerText = "Player 2 (O)";
}

```

### Display the player names and scores (your task)
You will need to keep track of each player's score. They should be set to zero (0) when the game begins. The scoring table should be updated with the player names and the scores should be displayed when we click the `New Game` button. Can you make this happen?

--- 

### Sir, I'm done...
Students who have this working - we need each square of the grid to call the **_same_** function: `game_click(event)`

But if all the squares call the same function, how do we know which square was clicked? [Research](https://www.google.com/search?q=html+javascript+Get+the+element+that+triggered+an+event) how to use the DOM `event` object to find out which square was clicked!


<br><br><br><br><br><br><br><br><br><br><br><br><br>