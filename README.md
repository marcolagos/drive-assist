# Drive Assist Feature

A car with drive assist that utilizes a BeagleBone and a camera to navigate along a blue taped path, programmed follow the path while maintaining a consistent speed, navigating 
turns, and coming to a brief stop at stop signs or red papers on the ground.

## Tuning Control Parameters

To achieve effective path following, a fine-tuning several control parameters, including resolution, proportional gain, and derivative gain.

- **Proportional Gain:** increased the proportional gain to make the car more responsive to errors.
- **Derivative Gain:** To reduce oscillations caused by high proportional gain, increased the derivative gain.
- **Resolution:** 160 x 120, with the camera initially set to 320 x 240 and resizing each frame in the loop.

The final values:
- Proportional Gain: 0.080
- Derivative Gain: 0.012

## Handling Stop Signs

Car was designed to handle stop signs, which are represented by red papers on the path. To detect and respond to stop signs, 
nalyze the color values in the camera feed to determine if the car sees red and if there's enough red to confirm the presence of a 
stop sign. "red" is falling within the color range of (140, 80, 170) to (200, 255, 250). These values were determined by 
examining the camera's output when viewing the red paper, which has a somewhat muted red appearance due to dust.

When the car detects a stop sign, it continues to move for a brief delay to reach the stop sign location before coming to a 
complete stop for a few seconds. After this pause, it resumes its path.

## Plots and Data

<img width="616" alt="image" src="https://github.com/marcolagos/self-driving-car/assets/84419908/057beecc-0877-43a2-a91c-d6c71ea5066f">
<img width="627" alt="image" src="https://github.com/marcolagos/self-driving-car/assets/84419908/66addd1b-61a1-4688-ad7d-9fc4b53e5676">

