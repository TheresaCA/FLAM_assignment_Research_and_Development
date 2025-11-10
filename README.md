### Problem Statement
Given a parametric equation of a curve:

$$
\begin{aligned}
x &= t \cos(\theta) - e^{M|t|}\sin(0.3t)\sin(\theta) + X \\
y &= 42 + t\sin(\theta) + e^{M|t|}\sin(0.3t)\cos(\theta)
\end{aligned}
$$

You are required to determine the unknown parameters:

$$
\theta \; M \; X
$$

using the provided dataset `xy_data.csv`.

---

### Approach

1. Load the dataset given into the ipynb file.

2. As the time values for x and y is not given split t which is in between the range (6,60) evenly amoung all points.

3.  Using the predicted x,y values and the actual x,y values calculate L1 loss. L1 loss refers to Manhattan distance which has the formula:

   <img width="430" height="92" alt="image" src="https://github.com/user-attachments/assets/a4f1b02f-eb87-4cbd-90f5-7adfd02f2953" />

   Thsi d_Manhattan is the L1 distance.

4. Find the optimized M, X and θ values using the L1 distance formula.

5. Find the x and y values with respect to the new t values, optimized M, X and θ values (becomes predicted x and y values using the formula given)


6. A plot between actual and predicted x,y values is made to check whether optimization is successfull or not


`the above steps are all in the ipynb file`

---

### Final Results

| Parameter | Symbol | Value |
|------------|---------|--------|
| Angle | θ | 0.4908 rad ≈ **28.13°** |
| Exponential factor | M | **0.0214** | 
| X-offset | X | **54.90** | 

---

### Final Equation

<img width="1135" height="66" alt="image" src="https://github.com/user-attachments/assets/b704d7d7-2e59-427c-8665-5b55605c0abe" />

which when spilt as x and y equations become

$$
\begin{aligned}
x(t) &= t \cos(0.4908) - e^{0.0214|t|}\sin(0.3t)\sin(0.4908) + 54.9008 \\
y(t) &= 42 + t\sin(0.4908) + e^{0.0214|t|}\sin(0.3t)\cos(0.4908)
\end{aligned}
$$

The graph looks like:
<img width="1128" height="796" alt="image" src="https://github.com/user-attachments/assets/54ed9655-60cf-4f85-abe3-01a925820960" />

---

### References

1. L1 loss - 
https://stevengong.co/notes/Manhattan-Distance#:~:text=Distance%20Metric%2C%20Heurisitic%20Function%20Manhattan%20Distance%20%28L1%20Loss%29,used%20for%20Computer%20Vision%3A%20d1%E2%80%8B%20%28I1%E2%80%8B%2CI2%E2%80%8B%29%3Dp%E2%88%91%E2%80%8B%E2%88%A3I1p%E2%80%8B%E2%88%92I2p%E2%80%8B%E2%88%A3%20Resources%20https%3A%2F%2Fpytorch.

