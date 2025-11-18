# Gimbal Lock Demonstration

An interactive 3D visualization that demonstrates the gimbal lock phenomenon using Three.js. This educational tool helps users understand how Euler angles can lose a degree of freedom when certain orientations are reached.

## Overview

Gimbal lock is a problem that occurs when using Euler angles for 3D rotations. When the middle axis (pitch) reaches ±90°, two of the three rotation axes become aligned, effectively losing one degree of rotational freedom. This demonstration visualizes this phenomenon using three nested gimbal rings.

## Features

- **Interactive 3D Gimbal System**: Three nested rings representing yaw (red), pitch (green), and roll (blue) rotations
- **Real-time Angle Display**: Live tracking of all three Euler angles in degrees
- **Gimbal Lock Detection**: Visual and textual warnings when gimbal lock occurs
- **Keyboard Controls**: Intuitive QWASDE key mapping for rotating each axis
- **Auto-demonstration Mode**: Automatic animation that showcases gimbal lock after 3 seconds of inactivity
- **Smooth Visuals**: Modern UI with glassmorphism effects and animations

## Controls

| Key | Action |
|-----|--------|
| **Q** | Rotate yaw (red ring) counterclockwise |
| **A** | Rotate yaw (red ring) clockwise |
| **W** | Increase pitch (green ring) |
| **S** | Decrease pitch (green ring) |
| **E** | Rotate roll (blue ring) counterclockwise |
| **D** | Rotate roll (blue ring) clockwise |

**Reset Button**: Click the "Reset View" button to return all angles to zero.

## Understanding Gimbal Lock

### What is Gimbal Lock?

Gimbal lock occurs when the pitch angle approaches ±90°. At this point:
- The yaw (outer red ring) and roll (inner blue ring) axes become parallel
- Two degrees of freedom effectively collapse into one
- Smooth rotation in certain directions becomes impossible
- The system loses the ability to represent certain orientations

### How to Trigger It

1. Use the **W** key to increase pitch toward +90°
2. Or use the **S** key to decrease pitch toward -90°
3. Watch for the red warning message and the central "GIMBAL LOCK" indicator
4. Notice how the red (yaw) and blue (roll) rings now rotate in similar ways

### Visual Indicators

- **Warning Panel**: Appears in the control panel when pitch is within 15° of ±90°
- **Central Lock Indicator**: A prominent "GIMBAL LOCK" message appears in the center of the screen
- **Ring Highlighting**: The outer (red) and inner (blue) rings glow when gimbal lock is detected
- **Pulsing Animation**: The warning panel pulses to draw attention

## Technical Details

### Technologies Used

- **Three.js (r128)**: 3D rendering and scene management
- **Vanilla JavaScript**: Core logic and interactivity
- **CSS3**: Modern UI styling with animations and effects

### Structure

- **Gimbal Hierarchy**: Three nested rings with parent-child relationships
  - Outer Ring (Red): Yaw rotation around Z-axis
  - Middle Ring (Green): Pitch rotation around Y-axis
  - Inner Ring (Blue): Roll rotation around X-axis
- **Coordinate Axes**: Visual representation of X, Y, Z axes in the center
- **Lighting System**: Ambient and directional lighting for depth perception

### Key Variables

- `euler.yaw`: Rotation around the vertical (Z) axis
- `euler.pitch`: Rotation around the lateral (Y) axis (clamped to ±90°)
- `euler.roll`: Rotation around the longitudinal (X) axis
- `angleStep`: Rotation increment per frame (0.03 radians)

## Installation & Usage

### Option 1: Direct File Usage
1. Download the HTML file
2. Open it in any modern web browser (Chrome, Firefox, Safari, Edge)
3. Start interacting using the keyboard controls

### Option 2: Local Server
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js http-server
npx http-server
```
Then navigate to `http://localhost:8000` in your browser.

## Browser Compatibility

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

Requires WebGL support for 3D rendering.

## Educational Use

This demonstration is ideal for:
- **Computer Graphics Courses**: Understanding rotation representations
- **Game Development**: Learning about camera and object orientation
- **Robotics Education**: Explaining mechanical gimbal systems
- **Aerospace Training**: Demonstrating aircraft orientation issues

## Troubleshooting

**Q: The 3D scene isn't loading**  
A: Ensure your browser supports WebGL and that hardware acceleration is enabled.

**Q: Controls aren't responding**  
A: Click anywhere on the page to ensure the window has focus, then try the keys again.

**Q: Auto-demo won't stop**  
A: Press any control key (Q, W, E, A, S, or D) to disable auto-demonstration mode.

## Future Enhancements

Potential improvements for this demonstration:
- Add quaternion rotation mode for comparison
- Include side-by-side visualization of Euler vs Quaternion
- Add preset orientations that trigger gimbal lock
- Include explanatory tooltips and guided tutorial
- Add mouse/touch controls for mobile compatibility

## License

This project is provided as-is for educational purposes. Feel free to modify and distribute with attribution.

## Additional Resources

To learn more about gimbal lock and rotation representations:
- [Wikipedia: Gimbal Lock](https://en.wikipedia.org/wiki/Gimbal_lock)
- [Understanding Quaternions](https://www.3dgep.com/understanding-quaternions/)
- [Euler Angles Documentation](https://threejs.org/docs/#api/en/math/Euler)

---

**Created with Three.js and passion for 3D mathematics** ⚙️
