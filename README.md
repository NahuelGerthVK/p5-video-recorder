# p5-video-recorder
This is a minimalist work in progress video recorder for p5.js using MediaRecorder API.

For feedback and improvement ideas feel free to reach out to [info@nahuelgerth.de](mailto:info@nahuelgerth.de)

---

![Preview](/preview.jpg)

---

## 🚀 Usage

1. **Import both `p5.js` and `export-video.js` in your `index.html`:**

```html
<!-- p5.js -->
<script src="libraries/p5.min.js"></script>

<!-- video export -->
<script src="export-video.js"></script>
```

2. **Create a recording button in your `index.html`:**
- You can use the classes if you want to keep the styling

```html
<div class="ui-group">
    <!-- button: record video -->
    <div class="ui-element">
        <label for="export-video-button">Record video</label>
        <div class="video-button-wrapper">

            <!-- start -->
            <button id="start-video-button" class="visible" onclick="startRecording()">&#9658; Start</button>
            
            <!-- stop -->
             <button id="stop-video-button" class="stop" onclick="stopRecording()">&#10074;&#10074; Stop</button>
        </div>
    </div>
</div>
```

- Otherwise all you need are those two buttons:

```html
<!-- start -->
<button id="start-video-button" onclick="startRecording()">&#9658; Start</button>

<!-- stop -->
 <button id="stop-video-button" onclick="stopRecording()">&#10074;&#10074; Stop</button>
```

3. **In your `sketch.js`:**
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