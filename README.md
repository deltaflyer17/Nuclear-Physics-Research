11 September 2026 - 09:38

Version 1 graphs with Powell optimization: 

Conditions used -

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

