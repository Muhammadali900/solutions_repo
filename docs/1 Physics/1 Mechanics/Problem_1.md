

---

## **Problem 1: Investigating the Range as a Function of the Angle of Projection**

### **1. Motivation**

Projectile motion, while seemingly simple, offers a rich playground for exploring fundamental principles of physics. The task is to analyze how the range of a projectile depends on its angle of projection. Although the problem appears straightforward, the governing equations of projectile motion involve both linear and quadratic relationships, which provide a deeper insight into the behavior of projectiles.

What makes this topic particularly compelling is the number of free parameters involved in these equations, such as:

- **Initial velocity** (\(v_0\))
- **Gravitational acceleration** (\(g\))
- **Launch height** (\(h\))

These parameters give rise to a diverse set of solutions that can describe a wide array of real-world phenomena, from the arc of a soccer ball to the trajectory of a rocket.

---

### **2. Theoretical Foundation**

The motion of a projectile can be described by the following equations, derived from the fundamental principles of Newtonian mechanics.

#### **2.1 Derivation of the Governing Equations**

When a projectile is launched with an initial velocity \(v_0\) at an angle \(\theta\), the motion can be broken into two components: horizontal motion (constant velocity) and vertical motion (under constant acceleration due to gravity).

1. **Horizontal Motion (constant velocity):**
   $$
   x(t) = $v_0$ \cos(\theta) \cdot t
   $$
   Where:
   - \(x(t)\) is the horizontal displacement at time \(t\),
   - \(v_0 \cos(\$theta$)\) is the horizontal component of the initial velocity.

2. **Vertical Motion (accelerated motion under gravity):**
   $$
   y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
   $$
   Where:
   - \(y(t)\) is the vertical displacement at time \(t\),
   - \(v_0 \sin(\theta)\) is the vertical component of the initial velocity,
   - \(g\) is the acceleration due to gravity.

#### **2.2 Time of Flight and Range**

The **time of flight** \(T\) is determined by when the projectile hits the ground, i.e., when \(y(T) = 0\). Solving for \(T\) gives:
$$
T = \frac{2 v_0 \sin(\theta)}{g}
$$

The **horizontal range** \(R\), which is the total horizontal distance traveled by the projectile, is obtained by multiplying the horizontal velocity by the time of flight:
$$
R = v_0 \cos(\theta) \cdot T = \frac{v_0^2 \sin(2\theta)}{g}
$$
Here, \(\sin(2\theta)\) arises from the trigonometric identity for the sine of a double angle.

#### **2.3 Analysis of the Range**

- The range \(R\) depends **non-linearly** on the angle \(\theta\).
- The range is **maximized** when the angle of projection is **\(\theta = 45^\circ\)** under ideal conditions (i.e., no air resistance).
- **Higher initial velocities** \(v_0\) increase the range.
- A **stronger gravitational field** (higher \(g\)) reduces the range.

---

### **3. Analysis of the Range**

The goal is to investigate how the horizontal range of a projectile depends on the launch angle \(\theta\). 

- **Variation with Launch Angle**: As the angle of projection changes, the range increases to a maximum value at \(45^\circ\) and then decreases symmetrically. This occurs because the velocity is split into horizontal and vertical components, and at \(45^\circ\), the components are balanced for maximum range.
  
- **Effect of Initial Velocity**: Increasing the initial velocity \(v_0\) increases the overall range for all values of \(\theta\), since the range is proportional to \(v_0^2\).

- **Effect of Gravitational Acceleration**: If the gravitational acceleration \(g\) increases (as it would on a planet with a stronger gravitational pull), the range decreases because the projectile falls back to the ground more quickly.


### **4. Implementation**

To simulate and visualize the projectile motion, we can create a computational tool that calculates the range for various angles of projection. Below is the Python script for the simulation.

```python
import numpy as np
import matplotlib.pyplot as plt

# Function to calculate projectile range
def projectile_range(v0, theta, g=9.81):
    theta_rad = np.radians(theta)  # Convert degrees to radians
    return (v0**2 * np.sin(2 * theta_rad)) / g  # Range formula

# Generate data for different angles
angles = np.linspace(0, 90, 100)  # Angles from 0 to 90 degrees
ranges = [projectile_range(20, theta) for theta in angles]  # Assuming v0 = 20 m/s

# Plot the range vs. angle graph
plt.figure(figsize=(8,5))
plt.plot(angles, ranges, label="Range vs. Angle")
plt.xlabel("Angle (degrees)")
plt.ylabel("Range (meters)")
plt.title("Projectile Range as a Function of Launch Angle")
plt.legend()
plt.grid()
plt.show()
```

---


 


