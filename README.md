# 3D Plot Projection Project

## Project Overview

This project visualizes randomly generated 3D points on a 2D canvas using **Orthographic** and **Perspective Projection** techniques. Users can interact with the visualization by rotating the scene using **Yaw**, **Pitch**, and **Roll** rotations.

---

## Features

* Random generation of 3D points
* Storage of points in a JSON file
* Orthographic Projection
* Perspective Projection
* Interactive 3D rotation using:

  * Pitch
  * Yaw
  * Roll
* Real-time animation using `requestAnimationFrame()`

---

## Workflow

```text
Random 3D Points
        ↓
Store in JSON
        ↓
Load in JavaScript
        ↓
Convert Degrees to Radians
        ↓
Apply Pitch, Yaw, and Roll
        ↓
Translate Along Z-Axis
        ↓
Apply Projection
        ↓
Draw on Canvas
        ↓
Animate
```

---

## Random Point Generation

Each point is generated with random **x**, **y**, and **z** coordinates and stored in a `data.json` file.

Example:

```json
{
  "x": 120,
  "y": -80,
  "z": 50
}
```

---

## Degree to Radian Conversion

JavaScript trigonometric functions require angles in radians.

### Formula

```text
Radians = Degrees × π / 180
```

---

## Rotation Equations

### Pitch Rotation (X-Axis)

```text
y' = y cosθ − z sinθ
z' = y sinθ + z cosθ
```

### Yaw Rotation (Y-Axis)

```text
x' = x cosθ + z sinθ
z' = −x sinθ + z cosθ
```

### Roll Rotation (Z-Axis)

```text
x' = x cosθ − y sinθ
y' = x sinθ + y cosθ
```

---

## Orthographic Projection

Orthographic projection ignores depth information.

### Formula

```text
X = x
Y = y
```

### Characteristics

* No perspective distortion
* Objects remain the same size regardless of distance
* Simple and fast rendering

---

## Perspective Projection

Perspective projection simulates how the human eye perceives depth.

### Formula

```text
Scale = f / (f + z)

X = x × Scale
Y = y × Scale
```

Where:

* `f` = focal length
* `z` = depth value

### Characteristics

* Distant objects appear smaller
* Creates realistic depth perception

---

## Implementation

### HTML

Provides:

* Canvas element
* Projection controls
* Rotation controls

### CSS

Responsible for:

* Page layout
* Styling
* User interface appearance

### JavaScript

Handles:

* Loading point data from JSON
* Degree-to-radian conversion
* Pitch, Yaw, and Roll calculations
* Orthographic and Perspective projections
* Canvas rendering
* Animation using `requestAnimationFrame()`

---

## Technologies Used

* HTML5
* CSS3
* JavaScript
* JSON
* HTML Canvas API

---

## Output

The project renders a rotating 3D scatter plot on a 2D canvas with selectable projection modes.

![Project Output](https://github.com/user-attachments/assets/96c302d2-bbe7-476a-b1e5-f0737ab94a29)

---

## Conclusion

This project demonstrates the complete 3D graphics pipeline, including random point generation, coordinate transformations, rotation matrices, projection techniques, and real-time visualization. It serves as a practical introduction to fundamental concepts used in computer graphics and game development.
