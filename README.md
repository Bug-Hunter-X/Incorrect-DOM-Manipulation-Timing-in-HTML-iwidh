# Uncommon HTML Bug: Incorrect DOM Manipulation Timing

This repository demonstrates a subtle bug related to the timing of DOM manipulation in HTML.  The script attempts to interact with an element before the element has been fully parsed by the browser, leading to unexpected behavior.

## Bug Description
The script attempts to hide a div element, but because the script tag is placed *before* the div element in the HTML structure, the browser hasn't yet created the div element in the DOM when the script tries to access it.  This results in the div not being hidden and, in some cases, could cause errors.

## Solution
The solution is simple: move the script tag to the end of the `<body>` element. This ensures that the entire HTML is fully parsed before the script attempts to manipulate any elements.