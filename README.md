11 September 2026 - 09:38

<h1> Version 1 graphs with Powell optimization: </h1> 

Conditions used -

Powell Time & Space Complexity

Time Complexity: O(n^2) 

<br>
Runtime: 13 minutes, 3 seconds, 8 milliseconds
<br>

Space Complexity: O(n* Tline)
where Tline is time taken to complete single 1-dimensional search

```python
fitter.chi2_LR_scale = 1e-4
fitter.chi2_PID_scale = 1
fitter.chi2_Ex_scale = 500
fitter.chi2_edges_scale = 100000

popt = scipy.optimize.minimize(fitter.eval_all, p0, method='Powell')

```



![Graph 1](global_fitter_edges.png)


![Graph 2](global_fitter_init.png)

![Graph 3](global_fitter_prog.png)

![Graph 4](global_fitter_final.png)


<h1> Using BFGS: </h1>

Runtime using BFGS: 14 minutes, 30 seconds

```Python
popt = scipy.optimize.minimize(fitter.eval_all, p0, method='BFGS')

```

![Graph 5](global_fitter_final.png)


<h1>Using Nelder-Mead Model </h1>
<br>
Runtime: 16 minutes, 3 seconds

![Graph 5](global_fitter_final.png)

<br>

<h1>Using Jacobian</h1>

```Python
def objective(params):
    return fitter.eval(params)

initial_params = fitter.params

res = minimize(
    fun=objective,
    x0=initial_params,
    method='BFGS',
    jac='3-point'
)
print("Starting gradient-based fit (BFGS)...")
print("Optimized parameters: ", res.x)

```
