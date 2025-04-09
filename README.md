# p5-video-recorder
This is a minimalist work in progress video recorder for p5.js using MediaRecorder API.

For feedback and improvement ideas feel free to reach out to [info@nahuelgerth.de](mailto:info@nahuelgerth.de)

---

## 🚀 Usage

1. **Import both `p5.js` and `export-video.js` in your `index.html`:**

```html
<!-- p5.js -->
<script src="libraries/p5.min.js"></script>

<!-- video export -->
<script src="export-video.js"></script>
```

2. **In your `sketch.js`:**
- Create your `canvas` as a global variable (so it’s accessible outside of `setup()`).
- Call `initRecorder(canvas)` inside `setup()`:
  
```js
let canvas;

/* - - Setup - - */
function setup() {
    
  // create canvas inside div
  canvas = createCanvas(500, 500);
  canvas.parent("canvas");

  // set up video export
  initRecorder(canvas);
}
```

- that should be it! :-)

## Notes
- **Chrome** will output `.webm` files
- **Safari** may fall back to `.mp4` files
- You can preview `.webm` files in most browsers or use a video converter to convert them to `.mp4`