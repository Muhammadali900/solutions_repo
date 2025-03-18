# Comprehensive Exploration of Projectile Motion

## 1. Fundamental Theoretical Concepts

Projectile motion is the movement of an object under the influence of gravity and its initial velocity. It's governed by the laws of physics and can be analyzed by dividing the motion into horizontal and vertical components.

---

### 1.1. Governing Equations of Motion
The motion follows Newton's laws and can be described by these fundamental equations:
1. **Horizontal displacement**:
   $$x = v_0 \cos(\theta) t$$
2. **Vertical displacement**:
   $$y = v_0 \sin(\theta) t - \frac{1}{2} g t^2$$
3. **Horizontal velocity**:
   $$v_x = v_0 \cos(\theta)$$
4. **Vertical velocity**:
   $$v_y = v_0 \sin(\theta) - g t$$

---

### 1.2. Additional Basic Formulas
- **Range (assuming flat terrain)**:
  $$R = \frac{v_0^2 \sin(2\theta)}{g}$$
- **Maximum height**:
  $$H = \frac{(v_0 \sin(\theta))^2}{2g}$$
- **Time of flight**:
  $$T = \frac{2v_0 \sin(\theta)}{g}$$
- **Trajectory equation**:
  $$y = x \tan(\theta) - \frac{g x^2}{2(v_0 \cos(\theta))^2}$$

---

### 1.3. Advanced Formulas
- **Range with air resistance (simplified)**:
  $$R \approx \frac{v_0^2 \sin(2\theta)}{g + \frac{C_d}{m}v_0 \cos(\theta)}$$
- **Range on an inclined plane**:
  $$R = \frac{2 v_0^2 \cos^2(\theta - \phi) \sin(\theta)}{g \cos(\phi)}$$
- **Energy relations**:
  - Kinetic energy:
    $$KE = \frac{1}{2} m (v_x^2 + v_y^2)$$
  - Potential energy:
    $$PE = m g y$$
  - Total energy:
    $$E = KE + PE$$
- **Rotational dynamics (if spinning)**:
  $$L = I \omega, \text{ where } I = \frac{2}{5}mr^2 \text{ for a sphere}$$

---

## 2. Python Code: Simulations and Visualizations

### 2.1. Basic Range Calculator
```python
import math

def calculate_range(v0, angle, g=9.8):
    angle_rad = math.radians(angle)
    return (v0**2 * math.sin(2 * angle_rad)) / g

# Example
range_result = calculate_range(20, 45)
print(f"Range: {range_result:.2f} meters")
2.2. Maximum Height and Time of Flight
python
def max_height_and_time(v0, angle, g=9.8):
    angle_rad = math.radians(angle)
    max_height = (v0**2 * math.sin(angle_rad)**2) / (2 * g)
    time_of_flight = (2 * v0 * math.sin(angle_rad)) / g
    return max_height, time_of_flight

# Example
height, time = max_height_and_time(20, 45)
print(f"Maximum Height: {height:.2f} meters")
print(f"Time of Flight: {time:.2f} seconds")
2.3. Range vs. Angle Plot
python
import numpy as np
import matplotlib.pyplot as plt

angles = np.linspace(0, 90, 500)
ranges = [calculate_range(20, angle) for angle in angles]

plt.plot(angles, ranges)
plt.title('Range vs. Angle of Projection')
plt.xlabel('Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid()
plt.show()
2.4. Simulation with Air Resistance
python
def simulate_with_air_resistance(v0, angle, Cd, mass, g=9.8, dt=0.01):
    angle_rad = math.radians(angle)
    vx, vy = v0 * math.cos(angle_rad), v0 * math.sin(angle_rad)
    x, y = 0, 0
    positions_x, positions_y = [x], [y]

    while y >= 0:
        drag_x = -Cd * vx**2
        drag_y = -Cd * vy**2
        ax = drag_x / mass
        ay = -g + drag_y / mass
        vx += ax * dt
        vy += ay * dt
        x += vx * dt
        y += vy * dt
        positions_x.append(x)
        positions_y.append(y)

    return positions_x, positions_y

x_vals, y_vals = simulate_with_air_resistance(20, 45, 0.05, 2)
plt.plot(x_vals, y_vals)
plt.title('Projectile Motion with Air Resistance')
plt.xlabel('Horizontal Distance (m)')
plt.ylabel('Vertical Distance (m)')
plt.grid()
plt.show()
2.5. Range on an Inclined Plane
python
def range_on_inclined_plane(v0, angle, incline_angle, g=9.8):
    angle_rad = math.radians(angle)
    incline_rad = math.radians(incline_angle)
    return (2 * v0**2 * math.cos(angle_rad - incline_rad)**2 * math.sin(angle_rad)) / (g * math.cos(incline_rad))

# Example
inclined_range = range_on_inclined_plane(20, 45, 30)
print(f"Range on Inclined Plane: {inclined_range:.2f} meters")
2.6. Energy Analysis Visualization
python
def energy_components(v0, angle, t, mass, g=9.8):
    angle_rad = math.radians(angle)
    vx = v0 * math.cos(angle_rad)
    vy = v0 * math.sin(angle_rad) - g * t
    kinetic_energy = 0.5 * mass * (vx**2 + vy**2)
    potential_energy = mass * g * (v0 * math.sin(angle_rad) * t - 0.5 * g * t**2)
    return kinetic_energy, potential_energy

times = np.linspace(0, 2, 500)
kinetic_energies = []
potential_energies = []

for t in times:
    ke, pe = energy_components(20, 45, t, 2)
    kinetic_energies.append(ke)
    potential_energies.append(pe)

plt.plot(times, kinetic_energies, label='Kinetic Energy')
plt.plot(times, potential_energies, label='Potential Energy')
plt.title('Energy Components Over Time')
plt.xlabel('Time (s)')
plt.ylabel('Energy (Joules)')
plt.legend()
plt.grid()
plt.show()
3. Limitations and Suggested Enhancements