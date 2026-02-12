# Advanced Flexbox Layout Decisions

## Dashboard Layout

One important decision I made was using `flex-direction: column` on the main dashboard container with `min-height: 100vh`. This allowed me to use `flex: 1` on the main content area so the footer stays at the bottom of the page (sticky footer pattern).

Inside each dashboard card, I used nested Flexbox with `flex-direction: column` and set the card body to `flex: 1`. This pushes the card footer to the bottom even when the content length is different between cards.

## Product Page Layout

For the top section, I used `display: flex` with `flex-wrap: wrap` so the gallery and info panel sit side-by-side on wide screens but stack on smaller screens.

For the specifications section, I used `flex: 1 1 200px` so spec items automatically wrap into new rows without media queries.

The reviews use the media object pattern. I gave the avatar a fixed width and set the content area to `flex: 1` with `min-width: 0` to prevent overflow issues.

## Article Layout

I used proportional sizing with `flex: 2 1 500px` for the article content and `flex: 1 1 300px` for the sidebar. This keeps the article larger while still allowing wrapping on smaller screens.

For the hero section, I used `flex-direction: column` and `margin-top: auto` to push the metadata to the bottom.

## Challenges

One challenge was controlling wrapping behavior without media queries. Understanding how `flex-basis`, `flex-grow`, and `flex-shrink` work together helped solve that. Testing at different screen sizes was important to fine-tune proportions.
