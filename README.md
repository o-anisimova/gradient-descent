This repository contains a NumPy-based implementation of the Gradient Descent algorithm designed to find the global minimum of the Rosenbrock function.

## Overview
The Rosenbrock function is a classic non-convex function used as a performance test for optimization algorithms. The global minimum is located at $(1, 1)$ inside a long, narrow, parabolic-shaped flat valley.

## Implementation Details

### Gradient Estimation
To improve numerical stability, the gradient is calculated using the **central difference method**. This approach provides a higher order of accuracy $O(h^2)$ compared to the standard forward difference:

$$f'(x) \approx \frac{f(x + h) - f(x - h)}{2h}$$

### Convergence Criteria
Rather than monitoring the change in function value, which can be misleading on flat surfaces, this implementation uses the **norm of the gradient**:

$$\|\nabla f(\mathbf{x})\| < \epsilon$$

The algorithm terminates only when the slope in all directions is near zero, ensuring a more reliable convergence to the global minimum.

## Parameters
* **Initial Point**: (5.0, 5.0)
* **Learning Rate**: 0.0001
* **Tolerance ($\epsilon$)**: $10^{-8}$
* **Step size ($h$)**: $10^{-5}$

## Results
The algorithm successfully converges to:
* **x**: 1.000...
* **y**: 1.000...
* **Function value**: $\approx 0$