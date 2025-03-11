$$  
# **Investigating the Range as a Function of the Angle of Projection**  

## **1. Motivation**  
  **Analyzing how the range of a projectile depends on its angle of projection.**  

 There are a number of **free parameters** involved in the equations, for example: 
- **Initial velocity (v₀)**  
- **Gravitational acceleration (g)**  
- **Launch height (h)**  

By adjusting these parameters, we can model various real-world situations, from the **trajectory of a soccer ball** to the **flight path of a rocket**.  

$$  

## **2. Theoretical Foundation**  
$$  

The motion of a projectile is governed by Newton’s equations of motion.  

### **2.1 Equations of Motion**  
For a projectile launched with an initial velocity **v₀** at an angle **θ**, the motion can be broken down into horizontal and vertical components:  

- **Horizontal motion (constant velocity):**  
  $$ x(t) = v_0 \cos(\theta) t $$  

- **Vertical motion (accelerated motion under gravity):**  
  $$ y(t) = v_0 \sin(\theta) t - \frac{1}{2} g t^2 $$  

The **time of flight** (T) is found by solving \( y(T) = 0 \):  
$$ T = \frac{2 v_0 \sin(\theta)}{g} $$  

The **horizontal range (R)** is:  
$$ R = v_0 \cos(\theta) \times T = \frac{v_0^2 \sin(2\theta)}{g} $$  

### **2.2 Analysis of the Range**  
- The range depends **non-linearly** on **θ** and is maximized at **θ = 45°** under ideal conditions.  
- Higher initial velocity **v₀** increases the range.  
- A stronger gravitational field **(higher g)** reduces the range.  

$$  

## **3. Python Simulation**  
$$  

Below is the Python code to simulate projectile motion and plot the **range vs. angle** graph:  

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

# **Analysis of Projectile Motion and Range Dependence on Angle**  

## **Theoretical Foundation**  
- The formula for range is given by:  
  $$ R = \frac{v_0^2 \sin(2\theta)}{g} $$  
- The range is **maximized at θ = 45°** under ideal conditions.  

## **Python Simulation**  
- We implemented a Python script to analyze the relationship between **launch angle and range.**  
- The script computes the range using **mathematical equations** and visualizes the results as a plot.  

## **Findings and Discussion**  
- The range increases until **θ = 45°**, then decreases symmetrically.  
- **Higher initial velocities** increase the range.  
- **Stronger gravity (e.g., on Jupiter)** reduces the range.  

 


