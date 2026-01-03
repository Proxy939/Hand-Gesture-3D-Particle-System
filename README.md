# Hand-Gesture-3D-Particle-System

Overview
The Hand Gesture Particle System is an interactive 3D visualization application that combines real-time hand tracking with dynamic particle animations. Users can control 5,000 animated particles through hand gestures captured via webcam or through manual slider controls.
Key Features

Real-time hand gesture recognition using MediaPipe Hands
5,000 interactive particles rendered with Three.js
5 unique particle formations: Hearts, Flowers, Saturn, Spiral, Fireworks
Smooth color transitions with HSL color space
Dual control modes: Gesture-based and manual sliders
Live visual feedback with hand skeleton overlay
Responsive design that adapts to window resizing


System Requirements
Browser Requirements

Google Chrome (recommended): Version 90+
Microsoft Edge: Version 90+
Firefox: Version 88+ (with reduced performance)
Safari: Version 14+ (gesture tracking may be limited)

Hardware Requirements

Webcam: Any USB or built-in camera (720p or higher recommended)
Processor: Dual-core CPU, 2.0 GHz minimum
RAM: 4GB minimum, 8GB recommended
Graphics: WebGL-compatible GPU

Network Requirements

Active internet connection for CDN resources:

Three.js library
MediaPipe Hands model
Camera utilities




Installation & Setup
Quick Start

Save the HTML file

Save the provided HTML code as particle-system.html
Ensure the file has .html extension


Open in Chrome

Right-click the file → "Open with" → Google Chrome
Or drag and drop the file into Chrome browser


Grant Camera Permission (when enabling tracking)

Click "Enable Camera Tracking" button
Allow camera access when prompted
Camera feed will appear in top-right corner



First-Time Setup
Without Camera:

The system works immediately with manual controls
Use sliders and buttons to interact with particles

With Camera:

Click "Enable Camera Tracking"
Allow browser to access webcam
Position yourself 2-3 feet from camera
Ensure good lighting for best tracking
Show your hand clearly to the camera


User Interface Guide
### UI Layout
- **Controls Panel (Top-Left):** Gestures, sliders, shape controls, camera toggle  
- **Camera Feed (Top-Right):** Live video with hand skeleton overlay  
- **Main Canvas:** 3D particle visualization  
- **Status Bar (Bottom):** Real-time system feedback 

Controls Panel (Top-Left)
Hand Gestures Section

Lists all available gesture controls
Color-coded gesture indicators
Real-time gesture names in cyan blue

Manual Controls Section

Expansion Slider: Controls particle spread (0.3x to 3x)
Color Shift Slider: Changes particle hue (0 to 360°)
Both sliders provide immediate visual feedback

Shapes Section

5 shape buttons in a grid layout
Active shape highlighted in pink
Click any button to switch shapes instantly

Camera Toggle Button

Pink button at bottom of panel
Text changes based on camera state
Shows error messages if camera fails

Camera Feed (Top-Right)
Video Preview

240x180 pixel mirror view
White border when inactive
Green border when hand detected

Hand Skeleton Overlay

Green lines connecting hand joints
Red dots at 21 landmark points
Updates at ~30 FPS

Status Bar (Bottom-Center)

Displays current action or gesture
Black background with blur effect
Updates in real-time with user actions


Hand Gesture Controls
Gesture Detection System
The system recognizes 5 distinct hand gestures using 21 hand landmarks tracked by MediaPipe. Each gesture must be held clearly for ~0.5 seconds to trigger.
Supported Gestures
1. ✊ Fist (Closed Hand)
Description: All fingers curled into palm, thumb tucked
Effect: Expands particles outward to 2.5x size
How to Perform:

Close all fingers tightly
Keep thumb against index finger
Hold steady for clear recognition

Visual Feedback:

Particles spread dramatically outward
Expansion slider moves to maximum
Status shows "Gesture detected: FIST"

Use Cases:

Creating dramatic expansive effects
Starting fireworks sequences
Emphasizing particle formations


2. ✋ Open Hand (All Fingers Extended)
Description: All five fingers spread apart and extended
Effect: Contracts particles inward to 0.5x size
How to Perform:

Extend all fingers fully
Spread fingers apart naturally
Keep palm facing camera
Thumb should be clearly separated

Visual Feedback:

Particles compress toward center
Expansion slider moves to minimum
Status shows "Gesture detected: OPEN"

Use Cases:

Creating tight, dense formations
Resetting particle spread
Transitioning between shapes


3. ✌️ Peace Sign (Victory/V-Sign)
Description: Index and middle fingers extended, others curled
Effect: Shifts color hue by 20% (72° on color wheel)
How to Perform:

Extend index and middle fingers only
Keep them separated in "V" shape
Curl ring, pinky, and thumb
Fingers should point upward

Visual Feedback:

Particles shift through color spectrum
Color slider updates automatically
Status shows "Gesture detected: PEACE"

Color Progression:

Blue → Purple → Pink → Red → Orange → Yellow → Green → Cyan → Blue

Use Cases:

Creating rainbow effects
Matching colors to music or themes
Exploring color combinations


4. 👍 Thumbs Up
Description: Thumb extended upward, all fingers curled
Effect: Cycles to next particle shape
How to Perform:

Extend thumb straight up or at angle
Curl all four fingers into palm
Keep fist closed tightly
Thumb should be clearly visible

Visual Feedback:

Instant shape transformation
Active shape button changes
Status shows new shape name
Smooth transition animation

Shape Cycle Order:

Hearts → 2. Flowers → 3. Saturn → 4. Spiral → 5. Fireworks → (back to 1)

Use Cases:

Quick shape switching
Exploring different formations
Performance sequences


5. 🤙 Shaka (Hang Loose)
Description: Thumb and pinky extended, three middle fingers curled
Effect: Activates Fireworks mode with 2x expansion
How to Perform:

Extend thumb outward
Extend pinky finger downward
Curl index, middle, and ring fingers
Hand can be rotated for comfort

Visual Feedback:

Immediately switches to Fireworks shape
Particles expand to 2x size
Status shows "FIREWORKS MODE!"
Creates explosive spherical pattern

Use Cases:

Dramatic finale effects
Celebration moments
Maximum visual impact


Gesture Recognition Tips
Optimal Hand Position:

Distance: 1.5 to 3 feet from camera
Angle: Palm facing camera directly
Position: Center of camera frame
Background: Plain, contrasting background

Lighting Requirements:

Bright, even lighting from front
Avoid backlighting (light behind you)
No harsh shadows on hand
Room lighting: 300+ lux recommended

Common Issues:

Gesture not detected: Hold longer, ensure fingers clearly extended/curled
Wrong gesture detected: Make gesture more distinct, separate fingers more
Flickering detection: Keep hand steadier, improve lighting
No detection: Check camera feed, ensure hand is visible


Manual Controls
Manual controls provide precise, slider-based control over particle behavior without requiring camera access.
Expansion Slider
Location: Controls panel, under "Manual Controls"
Range: 0.3x to 3.0x (default: 1.0x)
Function: Controls the spread/density of particles
Values:

0.3x - 0.7x: Tight, compact formations
0.8x - 1.2x: Natural, balanced spread
1.3x - 2.0x: Expanded, airy formations
2.1x - 3.0x: Maximum expansion, dramatic spread

How to Use:

Click and drag slider handle
Or click anywhere on slider track
Visual changes occur in real-time
Works independently of gestures

Keyboard Support:

Arrow keys: Fine adjustment (±0.1)
Page Up/Down: Large adjustment (±0.5)


Color Shift Slider
Location: Controls panel, below Expansion slider
Range: 0.0 to 1.0 (represents full HSL color wheel)
Function: Rotates particle colors through spectrum
Color Map:

0.0: Red
0.17: Orange/Yellow
0.33: Green
0.5: Cyan
0.6: Blue (default)
0.75: Purple
0.9: Magenta
1.0: Red (full circle)

How to Use:

Drag slider to desired color
Colors transition smoothly over ~2 seconds
Individual particles have slight hue variation
Creates gradient effect across formation

Color Harmony Tips:

Complementary: Set values 0.5 apart (e.g., 0.0 and 0.5)
Analogous: Small changes (±0.1)
Triadic: Values at 0.0, 0.33, 0.67
Warm tones: 0.0 - 0.2
Cool tones: 0.4 - 0.7


Shape Buttons
Location: Controls panel, "Shapes" section
Available Shapes: 5 buttons in grid layout
Interaction:

Click any button to switch immediately
Active button highlighted in pink
Inactive buttons in cyan
Hover effect: slight scale increase

Keyboard Shortcuts:

Numbers 1-5: Switch to corresponding shape
Spacebar: Next shape (cycles)
Shift+Spacebar: Previous shape


Particle Shapes
1. Hearts ❤️
Mathematical Basis: Parametric heart curve equation
Formation:
x = 16 × sin³(t)
y = 13cos(t) - 5cos(2t) - 2cos(3t) - cos(4t)
Characteristics:

5,000 particles forming heart outline
Depth variation: ±10 units
Slight randomization for organic feel
Rotates continuously on Y-axis

Best Settings:

Expansion: 1.0x - 1.5x
Colors: Red (0.0), Pink (0.9), Purple (0.75)

Use Cases:

Valentine's Day themes
Love messages
Romantic presentations
Emotional expressions

Performance: High (complex curve calculation)

2. Flowers 🌸
Mathematical Basis: Rose curve with 5 petals
Formation:
r = 10 × (1 + 0.5 × sin(5θ))
Petals = 5
Characteristics:

Radial symmetry
5 distinct petal formations
Shallow depth for flat appearance
Organic petal shapes

Best Settings:

Expansion: 0.8x - 1.3x
Colors: Pink (0.9), Yellow (0.15), Purple (0.75)

Variations:

Small expansion: Tight bud
Medium expansion: Full bloom
Large expansion: Wilting flower

Use Cases:

Nature themes
Spring presentations
Botanical visualizations
Decorative backgrounds

Performance: Medium (trigonometric calculations)

3. Saturn 🪐
Mathematical Basis: Sphere + toroidal ring
Formation Components:

Planet Core (30%): 1,500 particles in sphere

Radius: 6 units (30% of ring radius)
Spherical coordinate distribution


Ring System (70%): 3,500 particles in torus

Inner radius: 16 units
Outer radius: 24 units
Thickness: ±2 units



Characteristics:

Realistic planetary appearance
Flat ring plane (Y ≈ 0)
Dense core with sparse rings
Orbital rotation effect

Best Settings:

Expansion: 1.0x - 1.8x
Colors: Orange (0.1), Yellow (0.15), Blue (0.6)

Astronomical Accuracy:

Ring-to-planet ratio: ~2.5:1 (similar to real Saturn)
Particle density distribution
Ring gap simulation possible

Use Cases:

Space themes
Astronomy education
Sci-fi presentations
Planetary simulations

Performance: Medium-Low (sphere + ring calculations)

4. Spiral 🌀
Mathematical Basis: Archimedean spiral in 3D
Formation:
radius = t × 10
θ = t × 20
x = radius × cos(θ)
y = (t - 0.5) × 40  (vertical spread)
z = radius × sin(θ)
Characteristics:

20 complete rotations
Vertical range: -20 to +20 units
Increasing radius with height
DNA helix appearance

Best Settings:

Expansion: 0.8x - 2.0x
Colors: Any (creates gradient naturally)

Variations:

Small expansion: Tight helix
Large expansion: Loose spiral galaxy

Use Cases:

DNA visualizations
Galaxy simulations
Abstract art
Tornado/vortex effects
Time progression concepts

Performance: High (complex 3D calculations)

5. Fireworks 🎆
Mathematical Basis: Spherical explosion with radial distribution
Formation:
Random spherical coordinates
Radius: 0 to 20 units (random per particle)
Vertical offset: +10 units (upward launch)
Characteristics:

Explosive radial pattern
Centered slightly above origin
Variable particle distances
Resembles mid-burst firework

Best Settings:

Expansion: 1.5x - 3.0x (maximum impact)
Colors: Multiple rapid changes
Gesture: Shaka for instant activation

Effects:

Small expansion: Initial burst
Large expansion: Full explosion
Color cycling: Multicolor fireworks

Use Cases:

Celebrations
New Year events
Victory moments
Climactic reveals
Attention-grabbing displays

Performance: Low (simple random distribution)
Animation Tips:

Start with Fist gesture (expand)
Rapid Peace gestures (color changes)
Return to Open gesture (contract)
Repeat for multiple bursts


Shape Transition Behavior
Transition Smoothness:

Particle positions interpolate over 3 seconds
Colors fade smoothly (5 second transition)
No jarring jumps between shapes

Optimal Transition Sequence:

Hearts → Flowers (both organic)
Flowers → Saturn (radial to circular)
Saturn → Spiral (circular to helical)
Spiral → Fireworks (helical to explosive)

Performance Considerations:

Transitions briefly increase CPU usage
Complex shapes (Hearts, Spiral) may lag on weak GPUs
Smooth transitions require 60 FPS


Technical Architecture
Core Technologies
Three.js (r128)
Purpose: 3D rendering and particle system
Key Components:

Scene: Container for 3D objects
Camera: PerspectiveCamera at 75° FOV
Renderer: WebGLRenderer with antialiasing
Geometry: BufferGeometry for 5,000 particles
Material: PointsMaterial with vertex colors

Performance Optimizations:

BufferGeometry for GPU efficiency
Additive blending for glow effect
Size attenuation for depth perception
Minimal draw calls (single Points object)

Memory Usage:

Positions: 60KB (5000 × 3 × 4 bytes)
Colors: 60KB (5000 × 3 × 4 bytes)
Sizes: 20KB (5000 × 4 bytes)
Total: ~140KB for particle data


MediaPipe Hands (v0.4)
Purpose: Real-time hand landmark detection
Model Specifications:

Landmarks: 21 3D points per hand
Detection confidence: 50% minimum
Tracking confidence: 50% minimum
Processing speed: ~30 FPS on modern hardware

Landmark Index Map:
0:  Wrist
1-4:  Thumb (base to tip)
5-8:  Index finger
9-12: Middle finger
13-16: Ring finger
17-20: Pinky finger
Coordinate System:

X: 0.0 (left) to 1.0 (right)
Y: 0.0 (top) to 1.0 (bottom)
Z: Depth relative to wrist (negative = toward camera)

Processing Pipeline:

Video frame capture (640×480)
MediaPipe inference (~33ms)
Landmark normalization
Gesture classification
Action triggering
