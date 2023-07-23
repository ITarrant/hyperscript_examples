This example was created in Django but you can apply it to anything on the back end. Creating this came about while adding 'sign on glass' to a transport tracking system
that already uses HTMX and Hyperscript and I want to keep the amount of standard Javascript to a minimum as I feel Hypserscript is easier to read and understand (especially later when looking back).
You could easily do this on a single page on first load, but I wanted the flexibility of being able to load / use the canvas when I wanted on any page.

Page1.html sets up a button to load the contents of Page2.html using HTMX.
The page now contains the canvas element and a clear button. This is setup for touch events, but could be easily changed for mouse click events.
If you want to do something with the canvas after being drawn on, you can add a hidden input in a form and submit the canvas to the backend as a Base64 image.

<form>
  ...
  <canvas id="main"></canvas>
  <input hidden id="canvasImg" name="signature">
  <button class="btn btn-primary btn-sm" type="submit" id="actionSubmit"
      _="on click set #canvasImg's value to #main.toDataURL()">Perform Action</button>
</form>
