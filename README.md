# gesture-controlled-particles---threejs-mediapipe-particles
Native HTML5 implementation of hand tracking and 3D geometry morphing using MediaPipe Hands and Three.js BufferGeometry.
Quantum Particles: AI-Controlled 3D HologramsA real-time, gesture-controlled 3D particle system running entirely in the browser.This project fuses Computer Vision (MediaPipe) with High-Performance WebGL Graphics (Three.js) to create an interactive holographic experience.(Tip: Replace the link above with a screenshot or GIF of your running project

OverviewQuantum Particles is an interactive experiment that tracks your hand movements via webcam to manipulate 35,000+ individual particles in 3D space. Unlike standard particle systems, this uses mathematical target morphing to transition smoothly between complex shapes (Spheres, Hearts, Cubes, DNA Helices, Saturn) based on hand gestures.It runs natively in HTML5/JavaScript without heavy frameworks or backend servers.✨ Key Features🖐 AI Hand Tracking: Uses Google's MediaPipe Hands to detect wrist position, finger pinch, and fist closure in real-time.

Shape Morphing: Smoothly interpolates particle positions between mathematical formulas (Torus, Pyramid, Sphere, etc.).🔍 Depth-Based Zoom: Calculates the physical distance of your hand from the camera to dynamically zoom in and out of the scene.

Physics Interactions:Rotate: Move hand Left/Right/Up/Down to rotate the hologram.Explode: Clench your fist to trigger a "Supernova" expansion effect and color shift.Switch: Pinch (Index + Thumb) to cycle through different geometric templates.🎨 Dynamic Visuals: Custom glowing sprite textures and additive blending for a "Neon/Holographic" aesthetic.🛠 Tech StackLanguage: Vanilla JavaScript (ES6 Modules)3D Engine: Three.js (WebGL)Computer Vision: MediaPipe HandsEnvironment: Native Browser (No Node.js/Webpack build step required)

How to RunSince this project uses ES Modules and webcam access, it requires a local server (it will not work if you just double-click index.html).Option 1: VS Code (Recommended)Clone this repository.Install the "Live Server" extension in VS Code.Right-click index.html and select "Open with Live Server".Allow Camera permissions when prompted.Option 2: Python Simple ServerIf you have Python installed, you can run:Bash# 

 ControlsGestureActionMove Hand (X/Y)Rotates the 3D ObjectMove Hand (Z-Depth)Zooms In (Closer) / Zooms Out (Further)Pinch (👌)Morphs to the next shape (Sphere → Cube → Heart...)Fist (✊)Triggers "Explosion" mode and color shift
 
 How It Works (The Math)The system does not destroy and recreate particles. Instead, it maintains a single BufferGeometry with 35,000 vertices.Target Calculation: When a shape changes, a function calculates the destination (x, y, z) for every particle based on parametric equations (e.g., x = r * sin(phi) * cos(theta) for a sphere).The Loop: inside animate(), every particle moves 10% of the way to its target position every frame (lerp).Vision Integration: The webcam feed is processed to find landmarks. We calculate the Euclidean distance between the wrist and middle finger to estimate "depth" for the zoom effect.
 
 ContributingFeel free to fork this project! Some cool ideas to add:Audio Reactivity: Make particles pulse to microphone music.New Shapes: Add DNA Helix or Text morphing.Color Themes: UI controls to change the color palette.
 
 LicenseThis project is open-source and available under the MIT License.
