<!-- @format -->

List of events: https://developer.mozilla.org/en-US/docs/Web/Events

---

You can only have one event handler for a specific event type, but you can add multiple event listeners for it.

```
const button = document.querySelector(".btn")

button.onclick = () => {
  console.log("First event handler!");
};

button.onclick = () => {
  console.log("Second event handler!");
};
```

##### The output will be "Second event handler!", because the second one overrides the first handler- as JS is synchronous

---

Let’s repeat this experiment by using two "click" event listeners:

```
const button = document.querySelector(".btn")

button.addEventListener("click", () => {
  console.log("First event listener!");
});

button.addEventListener("click", () => {
  console.log("Second event listener!");
});
```

It is okay to have multiple event listeners of the same event per object. Thus, both of the listeners are triggered once a button is clicked:

---

Generally, it is advised to use event listeners over event handlers because you can add multiple event listeners for the same event.

---

Here are some of the most common events in JavaScript that you can handle:

_click_: Fired when an element is clicked.

_mouseover_: Fired when the mouse pointer is moved over an element.

_mouseout_: Fired when the mouse pointer is moved out of an element.

_keydown_: Fired when a key is pressed down.

_keyup_: Fired when a key is released.

_submit_: Fired when a form is submitted.

_change_: Fired when the value of an input element (such as `<input>`, `<select>`, or `<textarea>`) changes.

_focus_: Fired when an element receives focus.

_blur_: Fired when an element loses focus.

_load_: Fired when a resource (such as an image or a script) has finished loading.

_resize_: Fired when the browser window is resized.

_scroll_: Fired when an element is scrolled.

---

EXAMPLE:

```
<!DOCTYPE html>
<html>
<head>
  <title>Event Examples</title>
</head>
<body>
  <button id="myButton">Click Me</button>
  <div id="myDiv">Hover over me</div>
  <input type="text" id="myInput">
  <form id="myForm">
    <input type="text" id="myFormInput">
    <button type="submit">Submit</button>
  </form>
  <img src="image.jpg" id="myImage" alt="My Image">
  <textarea id="myTextarea"></textarea>

  <script>
    const button = document.getElementById('myButton');
    button.addEventListener('click', function(event) {
      console.log('Button clicked');
    });

    const div = document.getElementById('myDiv');
    div.addEventListener('mouseover', function(event) {
      console.log('Mouse over div');
    });

    div.addEventListener('mouseout', function(event) {
      console.log('Mouse out of div');
    });

    const input = document.getElementById('myInput');
    input.addEventListener('change', function(event) {
      console.log('Input value changed');
    });

    const form = document.getElementById('myForm');
    form.addEventListener('submit', function(event) {
      event.preventDefault(); // Prevent form submission
      console.log('Form submitted');
    });

    const image = document.getElementById('myImage');
    image.addEventListener('load', function(event) {
      console.log('Image loaded');
    });

    const textarea = document.getElementById('myTextarea');
    textarea.addEventListener('input', function(event) {
      console.log('Textarea input changed');
    });
  </script>
</body>
</html>
```
