# linkedin-invite-100
Automatically select 100 contact to invite to your page

```// Select all div elements with role="listbox"
var listboxes = document.querySelectorAll('div[role="listbox"]');

// Loop through each listbox
listboxes.forEach(function(listbox) {
  // Select all checkboxes inside the current listbox
  var checkboxes = listbox.querySelectorAll('input[type="checkbox"]');
  var count = 0; // Counter variable

  // Loop through each checkbox and simulate mousedown and click events for the first 100
  checkboxes.forEach(function(checkbox) {
    // Check if the counter has reached 100
    if (count >= 100) {
      return; // Break the loop if 100 checkboxes have been checked
    }

    // Trigger mousedown event
    var mousedownEvent = new MouseEvent('mousedown', {
      bubbles: true,
      cancelable: true,
      view: window
    });
    checkbox.dispatchEvent(mousedownEvent);

    // Trigger click event
    var clickEvent = new MouseEvent('click', {
      bubbles: true,
      cancelable: true,
      view: window
    });
    checkbox.dispatchEvent(clickEvent);

    count++; // Increment the counter
  });
});
```
