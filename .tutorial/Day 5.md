# Part 4 - The Event Object

Hopefully you have a grid of squares (images) that all call the same `game_click` function. **But how do we figure out _which_ element called the function?**

**Event listeners do more than just call the function.** They pass along important information. The **`event`** object gets passed to functions when an event is fired. ([w3schools event page](https://www.w3schools.com/jsref/obj_event.asp))

Let's add the `event` object as a _parameter_ to our function:
```JS
function game_click(event) {
  
}
```

We can name the `event` variable anything we want. Typical names include `e`, `evt`, and `event`. **But what can it do?**

- **`event.target`** - Returns the element that triggered the event
- **`event.currentTarget`** - Returns the element whose event listener triggered the event
- `event.createEvent()` - Creates a new event
- `event.isTrusted` - Returns whether or not an event was triggered by a human or a script
- `event.preventDefault()` - The default action that belongs to the event will not occur (like copy/paste or right-click)
- `event.timeStamp` - Returns the time (in milliseconds relative to the epoch) at which the event was created
- `event.type` - Returns the name of the event

**The first two items are important** - `currentTarget` and `target`. 

The `currentTarget` represents _the element that called the function_. That might not be the element you clicked.

The `target` represents _the element that was clicked_. If this element doesn't have an event listener, it might pass it on to any containers it sits in.

Both of those (`currentTarget` and `target`) are a _handle_ to the element that was clicked. This means you can get the `id` or any other attribute:
```JS
function game_click(event) {
  let item_clicked = event.target.id;
  let event_caller = event.currentTarget.id;
  // Those will be strings - the unique id you gave 
  // the element (or blank if no id was given)
  ...
}
```

That allows the developer to figure out which element called the `game_click` function and start providing logic and feedback to the user based on the program or game! Full interaction!


### Your Task

You now have everything you need.
- variables for the player names and scores
- a variable that keeps track of whose turn it is
- the ability to start a new game
- the ability to know which grid item was clicked
  - 🡱 this last one gives you the ability to start coding a functioning tic-tac-toe game!

1. Start each square with the blank image.
2. Set up your `game_click` function to change the clicked image based on whose turn it is (player 1 is X, player 2 is O).
3. Do not let a user click on an already selected square.
4. Once an image is revealed (X or O) change whose turn it is.


<br><br><br><br><br><br><br><br><br>