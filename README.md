# Drawing App

A simple, responsive canvas-based drawing app built with  JavaScript and Tailwind CSS CDN. Supports mouse and touch input, multiple colors, and a quick clear action.

—

## Features 

- Responsive canvas that scales with screen size
- Mouse and touch drawing support (mobile-friendly)
- Smooth lines with round caps and joins
- Quick color selection buttons (Black, Red, Blue, Green, Yellow)
- One-click Clear to erase the canvas
---
## DEMO
- [Drawing App]( https://haseebjaved4212.github.io/Drawing-App/)


## Tech Stack

- HTML5 Canvas
- JavaScript 
- Tailwind CSS via CDN

## Project Structure

```
Drawing App/
├─ index.html     # UI layout + Tailwind CDN + canvas element
├─ script.js      # Drawing logic (mouse/touch, colors, clear)
└─ README.md      # This documentation
```

## Getting Started

- Just open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).

## Usage

1. Pick a color by clicking a color circle.
2. Draw on the canvas by clicking and dragging (mouse) or swiping (touch).
3. Press Clear to erase everything.

## Controls

- Color buttons: Set the line color
- Clear: Wipes the entire canvas
- Line width: Default is 5px (see customization below)

## How it works

- The canvas context is initialized with round caps/joins and a default line width.
- Touch and mouse events are normalized to canvas coordinates using `getBoundingClientRect()` and canvas width/height.
- The canvas is resized responsively while keeping aspect ratio; drawing settings are re-applied after resize.

## Customization

Open `script.js` and adjust these lines as needed:

- Default line width:

  - Look for: `ctx.lineWidth = 5;` (appears in initial setup and after resize)
  - Change `5` to your preferred width.

- Add more colors:

  - In `index.html`, duplicate a color button block and change its `id` and `background-color` style.
  - The JS auto-binds click handlers to any element whose id starts with `color-`.

- Canvas size and aspect ratio:

  - `initialCanvasWidth = 800` and `initialCanvasHeight = 600` control the base aspect ratio.
  - Update both to change the default scale and ratio.

- Tailwind styling:
  - Modify classes in `index.html` to tweak spacing, borders, shadows, etc.

### Example: add a Purple color

In `index.html`, inside the color buttons group:

```html
<button
  id="color-purple"
  class="w-8 h-8 rounded-full border-2 border-transparent hover:border-black"
  style="background-color: #a855f7;"
></button>
```

No JS change needed; the listener uses `[id^="color-"]` to auto-detect.

## Accessibility

- Large touch targets (32px+) for color buttons
- High-contrast default colors against white canvas
- Touch gestures disabled for the canvas to avoid accidental scrolling while drawing


## Troubleshooting

- Canvas does not draw on mobile:
  - Ensure you are drawing inside the canvas area.
  - Some browsers require user interaction; reload and try again.
- Colors not changing:
  - Make sure you clicked the color circle. The active stroke color updates immediately.
- Canvas looks blurry on HiDPI:

  - You can scale the canvas by devicePixelRatio in JS for extra sharpness (optional enhancement).



## License 

- MIT License. Use freely with attribution if desired.

—

Made with ❤️ by You
