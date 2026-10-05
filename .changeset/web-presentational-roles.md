---
'@e2e-dev/web': patch
---

`role="presentation"` and `role="none"` are ignored on a control a person can focus or an element carrying a global ARIA state or property, so `<button role="none">` reads as a `button` in the tree and keeps its accessible name, and `<a href role="presentation">` stays the link `getByRole` finds. An `<img alt="">` that is focusable or carries an `aria-*` attribute is an `image` rather than decoration. A zero-size element a person can focus, an empty inline link, is listed with its `hidden` state set instead of being dropped, so a role or test-id locator reaches it while `toBeVisible` still calls it hidden.
