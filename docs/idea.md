Build a simple web application that renders a Mortal Kombat-style ladder UI using a reusable “step” image template and dynamically injected character portraits.



Core concept:



There is ONE base “step” image (a stone block).

The step image contains a solid green (#008000) rectangular area that marks where the portrait should appear.

A JSON file provides an ordered list of character portrait images.

A separate image is provided representing the PLAYER.

A separate image is provided representing the QUESTION MARK (top slot).



The app must dynamically render the ladder by inserting portraits into the step template.



Requirements:



Data Source

Load a JSON file containing an ordered array of portrait image URLs.

This array represents the ladder from bottom to top.

Also accept:

A "playerPortrait" image URL

A "questionMarkPortrait" image URL

Step Rendering System

Each ladder step must use the same base “step” image.

The green (#008000) area inside the step defines where the portrait goes.

The implementation must:

Overlay the portrait exactly in that region

Completely hide/cover the green area in the final result

Portrait Placement

Portrait must:

Fully cover the green area

Be clipped to that rectangular region

Maintain aspect ratio (use object-fit: cover)

Use CSS positioning (absolute inside relative container) or masking

Ladder Logic (CRITICAL)

Given N steps:

Step N (top):

→ Always display the questionMarkPortrait

Step N-1 (second-to-last):

→ Always display the playerPortrait

Steps 0 to N-2:

→ Display portraits from the JSON array in order



Note:



The JSON array should fill the ladder except for the last two steps

If there are more portraits than needed, truncate

If there are fewer, still render correctly

Layout

Render steps vertically in a centered column

Total number of steps should be driven by the JSON length + 2 (for player + question mark)

Steps should stack tightly to resemble a continuous tower

No Animation

The UI must be completely static

Responsiveness

The ladder must scale proportionally

Portrait placement must remain perfectly aligned with the green area at all sizes

Implementation Structure

Function to load JSON

Reusable function/component to render a step

Main function to assemble the ladder

Edge Cases

Handle very small lists (0 or 1 portraits)

Handle broken image URLs with placeholders

Ensure layout stability regardless of list size

Output

Provide full working code (HTML, CSS, JS)

Include clear comments explaining:

How portrait positioning maps to the green area

How ladder indexing works (especially last two steps)



Goal:

The final result should visually replicate a classic Mortal Kombat arcade ladder, with identical stone steps and dynamically inserted portraits, including a player slot just below a question-mark top slot.

