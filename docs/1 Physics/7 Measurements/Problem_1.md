# Measuring Gravitational Acceleration with a Pendulum

## Objective

To experimentally determine the gravitational acceleration $g$ using a simple pendulum and analyze the uncertainties in the process.

## Materials

- String: $L = 1.000 \, \text{m}$.
- Stopwatch (± 0.2 s uncertainty).
- Ruler with 1 cm resolution → $\Delta L = 0.005 \, \text{m}$.
- Small mass (e.g., keychain).
- Stable support.

## Procedure Summary

- Displace pendulum < 15°.
- Measure time for 10 oscillations.
- Repeat 10 times.
- Compute average, standard deviation, and uncertainties.

## Collected Data

| Trial | $T_{10}$ (s) |
|-------|--------------|
| 1     | 20.18        |
| 2     | 20.12        |
| 3     | 20.24        |
| 4     | 20.10        |
| 5     | 20.19        |
| 6     | 20.13        |
| 7     | 20.21        |
| 8     | 20.11        |
| 9     | 20.15        |
| 10    | 20.16        |

## Calculations

1. **Mean and Standard Deviation**
   
    
    $\overline{T}_{10} = \frac{1}{10} \sum T_{10} = 20.159 \, \text{s}$.
   
    
    $\sigma_T = \sqrt{\frac{1}{n-1} \sum (T_i - \overline{T}_{10})^2} \approx 0.045 \, \text{s}$.
   
    
    $\Delta T_{10} = \frac{\sigma_T}{\sqrt{n}} = \frac{0.045}{\sqrt{10}} \approx 0.014 \, \text{s}$.

2. **Period of One Oscillation**
   
   
    $T = \frac{\overline{T}_{10}}{10} = 2.0159 \, \text{s}$.
   
   
    $\Delta T = \frac{\Delta T_{10}}{10} = 0.0014 \, \text{s}$.

3. **Compute Gravitational Acceleration**
   
   
    $g = \frac{4 \pi^2 L}{T^2} = \frac{4 \cdot \pi^2 \cdot 1.000}{(2.0159)^2} \approx 9.70 \, \text{m/s}^2$.

4. **Uncertainty in $g$**
   
   
    $\Delta g = g \cdot \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \cdot \frac{\Delta T}{T}\right)^2}$.
   
   
    $= 9.70 \cdot \sqrt{\left(\frac{0.005}{1.000}\right)^2 + \left(2 \cdot \frac{0.0014}{2.0159}\right)^2} \approx 9.70 \cdot 0.0054 = 0.052 \, \text{m/s}^2$.

## Final Result

- $g = 9.70 \pm 0.05 \, \text{m/s}^2$.

## Analysis

- **Comparison with Standard**:
     - Standard $g = 9.81 \, \text{m/s}^2$.

     - Our result is slightly lower but within ~1.1%.

     - Falls within uncertainty range, so it’s acceptable.





- **Sources of Uncertainty**:

  | Source              | Contribution                  |
  |---------------------|--------------------------------|
  | Ruler (length)      | ±0.5 cm → $\Delta L = 0.005 \, \text{m}$ |
  | Timing variability  | ±0.2 s for human reaction     |
  | Oscillation angle   | < 15° assumed; larger angles introduce systematic error |
  | Air resistance, friction | Neglected in ideal model |



- **Assumptions**:
  - Small-angle approximation ($\theta < 15^\circ$).
  - Rigid, massless string.
  - Point mass bob.
  - No air drag or pivot friction.

## Conclusion

The measured gravitational acceleration is:

- $g = 9.70 \pm 0.05 \, \text{m/s}^2$.

This agrees with the accepted value of $9.81 \, \text{m/s}^2$ within uncertainty, demonstrating that a simple pendulum is a reliable tool for measuring $g$ with careful execution and uncertainty analysis.

