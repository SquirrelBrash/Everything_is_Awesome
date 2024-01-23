# Part 1 - Tables
### Tic-Tac-Toe

Wouldn't it be great if we could make a game of tic-tac-toe? **But we have to start small - how do we get that nice 3x3 setup?**

**[HTML Tables](https://www.w3schools.com/html/html_tables.asp)** are a great way to organize information into a grid.

It starts with the `<table>` tag (there is an option for border size):
```HTML
<table border=1>
  
</table>
```
Tables are made up of **_rows_**. You can have as many rows as you want. To create a row, use the `<tr>` tag:
```HTML
<table border=1>
  <tr>
    
  </tr>
</table>
```

But in order to have a square (or "cell") we need to add a "table data" tag `<td>`:
```HTML
<table border=1>
  <tr>
    <td>
      Anything you put in here shows up in the table.
    </td>
  </tr>
</table>
```

You can have as many `<td>`'s as you want in a row:
```HTML
<table border=1>
  <tr>
    <td>
      Anything you put in here shows up in the table.
    </td>
    <td>
      This is another cell.
    </td>
  </tr>
</table>
```

The game of tic-tac-toe has **3** rows. And each row has **3** columns (cells).

Let's make a _front-end_ for a tic-tac-toe game.
1. Start by giving your page a meaningful `<title>`
  <br>
  
2. Now put a _heading_ on your page so people know what they're looking at. Something as simple as **Tic-Tac-Toe** will do.
  <br>
  
3. Create the table for your 3x3 tic-tac-toe grid. _Don't worry that it's not centered on the page or that it looks ugly. Style comes later._
  <br>
  
4. In each `<td>` put some text so you can see the table. Someting as simple as the coordinates (0, 0)  (0, 1), etc... will do. **Remember, in computer science (0,0) is the top LEFT corner.**

  
If you are feeling adventurous, insert the [blank.png](#images/blank.png) image into each `<td>` instead of the text - but this is optional.

---

<br><br>

**Styling Tables:** if you want to give your table a certain look, you will need to use CSS. [Here is a great place to start](https://www.w3schools.com/css/css_table.asp).

<br><br><br><br>
<br><br><br><br>
