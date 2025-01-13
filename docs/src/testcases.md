# List of test cases
The following table contains all test cases currently available in the benchmark suite.
When implementing one of these into the MC sampling framework of your choice, you can use the given testpoints to validate your implementation.  
We provide example implementations of the listed test cases to be used with Julia, Python, R and Stan.  
*This table is not yet complete and will be extended* 
| Name                            | Equation                                                                                                                                                                                                                   | Parameters                                | Testpoints                                                                                        | Julia | Python | R   | Stan |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------ | ----- | ------ | --- | ---- |
| Standard Normal 1D              | $f(x\|\mu, \sigma) =\frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}$                                                                                                                                      | $\mu = 0, \sigma = 0$                     | $f(x=0) = 0.39894228$, $f(x=1) = 0.24197072$                                                     | ✅     |    ✅     |  ✅    |   ✅    |
| Standard Normal 2D Uncorrelated | $f(x\| \boldsymbol\mu, \boldsymbol\Sigma) = (2\pi)^{-k/2}\det (\boldsymbol\Sigma)^{-1/2} \exp \left( -\frac{1}{2} (\mathbf{x} - \boldsymbol\mu)^\mathrm{T} \boldsymbol\Sigma^{-1}(\mathbf{x} - \boldsymbol\mu) \right)$ | $k=2, \mu=\texttt{zeros(2)}, \Sigma= I_2$ | $f(x=[0, 0]) = 0.15915494$, $f(x=[0, 1]) = 0.096532352$, $f(x=[-1, 1]) = 0.0585498315$           | ✅     |   ✅      |  ✅    |   ✅    |
| Standard Normal 3D Uncorrelated | $f(x\| \boldsymbol\mu, \boldsymbol\Sigma) = (2\pi)^{-k/2}\det (\boldsymbol\Sigma)^{-1/2} \exp \left( -\frac{1}{2} (\mathbf{x} - \boldsymbol\mu)^\mathrm{T} \boldsymbol\Sigma^{-1}(\mathbf{x} - \boldsymbol\mu) \right)$ | $k=3, \mu=\texttt{zeros(3)}, \Sigma= I_3$ | $f(x=[0, 0, 0]) = 0.063493636$, $f(x=[1, 1, 1]) = 0.014167345$, $f(x=[-1, 0, 1]) = 0.0233580033$ | ✅     |  ✅       |  ✅    |   ✅    |




# List of metrics
The following metrics are available to compare custom generated MC samples to IID samples.

## One-sample metrics
- Marginal mean: `marginal_mean()`
- Marginal variance: `marginal_variance()`
- Global mode: `global_mean()`
- Marginal mode: `marginal_mode()`
- Marginal skewness: `marginal_skewness()`
- Marginal kurtosis: `marginal_kurtosis()`

## Two-sample metric
- Chi-squared: `chi_squared()`
- Sliced Wasserstein Distance: `sliced_wasserstein_distance()`
- Maximum Mean Discrepancy: `maximum_mean_discrepancy()`
