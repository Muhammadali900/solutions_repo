### Problem 1: Investigating the Range as a Function of the Angle of Projection

---

#### 1. Theoretical Foundation

Projectile motion follows from the basic equations of motion under constant acceleration. The equations of motion are:

- **Horizontal motion**:  
  $$
  x(t) = v_0 \cos(\theta) t
  $$

- **Vertical motion**:  
  $$
  y(t) = v_0 \sin(\theta) t - \frac{1}{2} g t^2
  $$

To find the time of flight $t_f$, we set $y(t_f) = 0$ (i.e., when the projectile hits the ground):

$$
0 = v_0 \sin(\theta) t_f - \frac{1}{2} g t_f^2
$$

Solving for $t_f$, we get:

$$
t_f = \frac{2 v_0 \sin(\theta)}{g}
$$

Substituting $t_f$ into the equation for $x(t)$, we can find the horizontal range $R$:

$$
R = \frac{v_0^2 \sin(2\theta)}{g}
$$

This is the formula for the **range of a projectile** as a function of the launch angle $\theta$.

---

#### 2. Analysis of the Range

From the derived equation for range:

$$
R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
$$

We can see that the range depends on:
- The initial velocity $v_0$,
- The gravitational acceleration $g$,
- The angle of projection $\theta$.

- The **sine of double the angle** $\sin(2\theta)$ gives a characteristic curve where the range is maximized when $\theta = 45^\circ$.
- If the initial velocity increases, the range increases proportionally.
- The range is inversely proportional to gravity; the higher the gravitational acceleration, the shorter the range.

---

#### 3. Practical Applications

In real-world situations, the model can be adapted for:
- **Uneven terrain**: The launch angle might need to be adjusted for different elevations.
- **Air resistance**: This introduces a drag force that slows down the projectile, especially at higher velocities.

To account for these factors, more advanced models are required, such as:
- **Drag force models** (e.g., quadratic drag for high velocities),
- **Simulation of motion on curved surfaces** (e.g., hills).

---

#### 4. Implementation 

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
