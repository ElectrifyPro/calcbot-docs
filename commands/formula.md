---
description: c-formula
---

# Formula

`c-formula` allows you to access common formulas used in math and solve for the unknowns in those formulas. The full list of formulas you can use is available at the bottom of this page. You can suggest a new formula to be added with the `c-featurerequest` command.

Here is a nice GIF that demonstrates the use of `c-formula` to solve for a variable:

![Using the Pythagorean Theoreom formula in c-formula to solve for the hypotenuse of a triangle](../assets/formula.gif)

## Formulas

Formulas are listed in the format: `id` - **Formula name**: `definition`.

### Algebra

* `exgd` - **Exponential growth**: `y(t) = a × e^(k × t)`
* `eci` - **Compount interest**: `A = P × (1 + r ÷ n)^(n × t)`
* `quad` - **Quadratic formula**: `x = (-b ± √(b^2 - 4 × a × c)) / (2 × a)`

### Chemistry

* `igl` - **Ideal gas law**: `P × V = n × R × T`

### Geometry

* `hf` - **Heron's formula**: `p = (a + b + c) ÷ 2; A = sqrt(p × (p - a) × (p - b) × (p - c))`
  * Computes the area of a triangle given its three sides.
  * The variable `p` represents half of the triangle's perimeter.
* `pyt` - **Pythagorean theorem**: `a^2 + b^2 = c^2`
* `rps` - **Regular polygon area \(from side\)**: `A = (s^2 × n) ÷ (4 × tan([180 | π] ÷ n))`
* `rpr` - **Regular polygon area \(from radius\)**: `A = r^2 × n × sin([360 | 2π] ÷ n) ÷ 2`
* `rpa` - **Regular polygon area \(from apothem\)**: `A = a^2 × n × tan([180 | π] ÷ n)`
* `sf` - **Slope formula**: `s = (y_2 - y_1) ÷ (x_2 - x_1)`
  * Computes the slope between two points.
* `tts` - **Triangle area \(from sides & angle\)**: `A = 0.5 × s_1 × s_2 × sin(a_3)`

### Physics

* `hook` - **Hooke's law**: `F_s = k × x`
* `knm1` - **Kinematic equation \(v, v\_0, a, t\)**: `v = v_0 + a × t`
* `knm2` - **Kinematic equation \(Δx, v, v\_0, t\)**: `Δx = t × (v + v_0) ÷ 2`
* `knm3` - **Kinematic equation \(Δx, v\_0, a, t\)**: `Δx = v_0 × t + 0.5 × a × t^2`
* `knm4` - **Kinematic equation \(Δx, v, v\_0, a\)**: `v^2 = v_0^2 + 2 × a × Δx`
* `lug` - **Law of universal gravitation**: `F = G × m_1 × m_2 ÷ r^2`
* `cenf` - **Centripetal force**: `F = m × v^2 ÷ r`

### Trigonometry

* `tlos` - **Law of sines**: `sin(A) ÷ a = sin(B) ÷ b`
* `tloc` - **Law of cosines**: `a^2 = b^2 + c^2 - 2 × b × c × cos(A)`

