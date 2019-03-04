# Ionic-Keyboard-Padding-Repro

## Issue #1

The keyboard offset on iOS devices doesn't look like it's the right size, the bottom padding is bigger than the top padding of `ion-content` when the keyboard is present.

Repro:

1. Focus the text field to trigger the keyboard.

## Issue #2

It's possible to scroll past the end of the content when the keyboard is present. Once you've scrolled past the end it can be difficult to get it to scroll back to the top of the content.

Repro:

1. Focus the text field to trigger the keyboard.
2. Scroll near the edge of the screen to scroll past the end (takes a few tries).
3. Try to scroll like normal and most of the content is off the top of the page.

### A workaround

I've found a workaround for this, but it likely won't behave well when built for iOS rather than a web app.

```
ion-content {
    --keyboard-offset: 0px !important;
}
```
