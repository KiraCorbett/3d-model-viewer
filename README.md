# 3D Model Viewer
The goal of this API is to make it easy to add 3D models to your webpages. The 3D Model Viewer is a web component that allows you to host the model on your site and provide an interactive way for users to explore the 3D model. 

![Project](/images/page-demo.png)

## Getting Started

This “How-To” will demonstrate how to get started with the 3D model viewer as well as implement a few features including staging/environment configurations, CAD model interactivity, and AR support. 

### Required Setup

* Web Browser
* Node Package Manager (npm)
* HTML, CSS, JavaScript

### Installations

You can use your own local web server or install [Node.js.](https://nodejs.org/en/). If you install Node, run the following command to install serve: 

```
npm install -g serve
```
Now you can clone this sample project. 

```
git clone https://github.com/KiraCorbett/3d-model-viewer.git
```

End with an example of getting some data out of the system or using it for a little demo

### Running this sample project

"cd" to your project directory (or where you cloned this project.) Inside the cloned directory, run the ```serve``` command to start a local web server. You may have to run  ``` npx serve ``` or ```npm run serve```. You should get an indication that your server is running and you can now copy the link provided by your server to access your project. 

![Serve](/images/serve.png)


## Starting your own project
 Create a static webpage or open the existing example index.html file provided in this project. To support all browsers, you will need to add the following set of JavaScript files in order to use the <model-viewer> in your <body>.

```
<!-- Include both scripts below to support all browsers! -->

<!-- Loads <model-viewer> for modern browsers: -->
<script type="module"
    src="https://unpkg.com/@google/model-viewer/dist/model-viewer.js">
</script>

<!-- Loads <model-viewer> for old browsers like IE11: -->
<script nomodule
    src="https://unpkg.com/@google/model-viewer/dist/model-viewer-legacy.js">
</script>
```
Note: You may see some errors in your DevTools web console through your browser. Google notes this is expected until the API is fully released. 

## Additional compatibility
You can add more compatibility by pasting the following code into <head>
```
<!-- The following libraries and polyfills are recommended to maximize browser support -->
<!-- NOTE: you must adjust the paths as appropriate for your project -->
    
<!-- REQUIRED: Web Components polyfill to support Edge and Firefox < 63 -->
<script src="https://unpkg.com/@webcomponents/webcomponentsjs@2.1.3/webcomponents-loader.js"></script>

<!-- OPTIONAL: Intersection Observer polyfill for better performance in Safari and IE11 -->
<script src="https://unpkg.com/intersection-observer@0.5.1/intersection-observer.js"></script>

<!-- OPTIONAL: Resize Observer polyfill improves resize behavior in non-Chrome browsers -->
<script src="https://unpkg.com/resize-observer-polyfill@1.5.1/dist/ResizeObserver.js"></script>

<!-- OPTIONAL: Fullscreen polyfill is required for experimental AR features in Canary -->
<!--<script src="https://unpkg.com/fullscreen-polyfill@1.0.2/dist/fullscreen.polyfill.js"></script>-->

<!-- OPTIONAL: Include prismatic.js for Magic Leap support -->
<!--<script src="https://unpkg.com/@magicleap/prismatic@0.18.2/prismatic.min.js"></script>-->
```

## Adding the model viewer

The 3D model viewer is similar to an html <img> or <video> tag. You can add a variety of attributes within the tag to provide animations interactivity, and even AR support for your users. 

Let's take a look at our first CAD model in this project (the badger in the snowy scene.) 

```
  <model-viewer
    src="/assets/badger/Badger.gltf" 
    alt="Badger">
  </model-viewer>
```

All you need to do to display the badger is identify the source directory. Now, if you run your server with npm, you should see the badger display in your webpage. 

**Note about CAD models** - The models utilize either a .gltf or .glb file. These files can usually be used interchangeably but they are required for the model viewer as it provides compatibility across devices and browsers. 

## Adding features

* Camera control
* Background colors and environments
* Lighting effects

```
<model-viewer id="camera-orbit" camera-controls autoplay
    src="/assets/badger/Badger.gltf" 
    background-color="#080808"
    background-image="snowy_park.hdr"
    shadow-intensity="1"
    camera-orbit="-75deg 75deg 25m"
    alt="Badger">
  </model-viewer>
```

## AR Support

On supported devices, the ```ar```m ```ios-src```, and other platform attributes can provide AR support. 

![Mobile Demo](/images/mobile-demo.jpeg)

```
<model-viewer id="camera-orbit" camera-controls autoplay
    src="/assets/badger/Badger.gltf" 
    ar
    ios-src
    background-color="#080808"
    background-image="snowy_park.hdr"
    shadow-intensity="1"
    camera-orbit="-75deg 75deg 25m"
    alt="Badger">
  </model-viewer>
```

### Resources

## Project resources
* [Google's Model-Viewer Web Component](https://developers.google.com/web/updates/2019/02/model-viewer)
* [Documentation](https://googlewebcomponents.github.io/model-viewer/index.html)

## Stock models and images
* [Polyfab](https://poly.google.com/)
* [Sketchfab](https://sketchfab.com/feed)
* [HDRIHaven](https://hdrihaven.com/)

### Project Credits
