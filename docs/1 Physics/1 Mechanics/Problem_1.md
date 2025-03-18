# Problem 1: Investigating the Range as a Function of the Angle of Projection

---

### 1. Theoretical Foundation

Projectile motion is governed by two main equations: horizontal and vertical motion.

#### Horizontal Motion:

$$
x(t) = v_0 \cos(\theta) t
$$

#### Vertical Motion:

$$
y(t) = v_0 \sin(\theta) t - \frac{1}{2} g t^2
$$

The time of flight \( t_f \) is found by setting \( y(t_f) = 0 \):

$$
t_f = \frac{2 v_0 \sin(\theta)}{g}
$$

#### Range Equation:

Substituting \( t_f \) into the horizontal motion equation:

$$
R = v_0 \cos(\theta) t_f = \frac{v_0^2 \sin(2\theta)}{g}
$$

---

### 2. Analysis of the Range

- The range \( R \) is a function of the launch angle \( \theta \), initial velocity \( v_0 \), and gravitational acceleration \( g \).
- The **maximum range** occurs at \( \theta = 45^\circ \), because:

$$
\sin(2 \times 45^\circ) = 1
$$

Thus, the range is maximized when the angle is \( 45^\circ \).

---

### 3. Practical Applications

In real scenarios, additional factors like air resistance and uneven terrain modify the ideal range equation. The formula becomes more complex as we incorporate:

- **Drag force**: \( F_d = \frac{1}{2} C_d \rho A v^2 \),
- **Uneven terrain**: Adjust launch angle based on height differences.

---

### 4. Implementation (Python Code)

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # Gravitational acceleration (m/s^2)
v_0 = 20  # Initial velocity (m/s)

# Function to calculate range
def calculate_range(v_0, theta, g):
    return (v_0**2 * np.sin(2 * np.radians(theta))) / g

# Angles for simulation (from 0 to 90 degrees)
angles = np.linspace(0, 90, 500)

# Calculate ranges for each angle
ranges = calculate_range(v_0, angles, g)

# Plot the range as a function of the angle
plt.figure(figsize=(8, 6))
plt.plot(angles, ranges, label=f'v0 = {v_0} m/s', color='blue')
plt.title("Range of a Projectile as a Function of the Launch Angle")
plt.xlabel("Launch Angle (degrees)")
plt.ylabel("Range (meters)")
plt.grid(True)
plt.legend()
plt.show()
