# Lissajous Figure Generator & Animator

This project contains two HTML files that demonstrate Lissajous figures using JavaScript and HTML Canvas.

## Files

### 1. `index.html` - Gen AI created by Gemini 2.5 Pro demo - Lissajous Figure Generator

*   **Purpose**: This file generates and animates Lissajous figures where the animation is achieved by continuously changing the phase of the parametric equations. This creates an effect of the figure itself evolving or rotating over time.
*   **Controls**:
    *   Frequency A (ω<sub>a</sub>)
    *   Frequency B (ω<sub>b</sub>)
    *   Phase (δ) (in degrees)
    *   Amplitude X (A)
    *   Amplitude Y (B)
    *   Animation Speed
    *   Line Width
    *   Line Color
*   **Animation Method**: The animation parameter `t` is incorporated into the phase component of the sine functions:
    *   `x(currentTime) = centerX + amplitudeX * Math.sin(a * currentTime + phase_degrees_to_radians + t_animation * animationSpeed);`
    *   `y(currentTime) = centerY + amplitudeY * Math.sin(b * currentTime + t_animation * animationSpeed);`
    (Note: The original `index.html` applies the `t_animation * animationSpeed` to both x and y, but one is added to the `phase` term and the other is directly added to `b * currentTime`. The description above captures the general idea of phase shifting for animation).

### 2. `index2.html` - Gen AI created by Gemini 2.5 Pro demo - Lissajous Figure Animator (Same prompt - attempt 2)

*   **Purpose**: This file also generates and animates Lissajous figures. However, its animation approach focuses on tracing the path of a statically defined Lissajous curve over time. The shape of the curve is determined by the parameters, and the animation draws this shape progressively.
*   **Controls**:
    *   Frequency X (a)
    *   Frequency Y (b)
    *   Phase (δ) (as a multiple of π)
    *   Amplitude X (A)
    *   Amplitude Y (B)
    *   Animation Speed
    *   Line Width
    *   Line Color
*   **Animation Method**: The animation progresses by incrementing a time variable `t`. The curve is drawn based on the parametric equations:
    *   `x(currentTime) = centerX + params.A * Math.sin(params.a * currentTime + params.delta);`
    *   `y(currentTime) = centerY + params.B * Math.sin(params.b * currentTime);`
    where `currentTime` is derived from the global animation time `t` and an offset to trace the curve. The underlying Lissajous figure's parameters (a, b, delta) remain constant during the tracing animation for a given set of inputs.
*   **Equations Displayed**: The page displays the standard Lissajous equations: $x(t) = A \sin(at + \delta)$, $y(t) = B \sin(bt)$.

## How to Use

1.  Clone or download the repository.
2.  Open either `index.html` or `index2.html` in a web browser.
3.  Use the sliders and color picker to adjust the parameters and observe the changes in the Lissajous figure. 



## Prompt sent to Gemini 2.5 Pro

> `Generate a single page html, javascript, and css demonstration of a Lissajous figure as an animation, including several variables that the user can adjust. This web app should be simple enough to host as a GitHub page.'