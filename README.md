# Analyzing the impact of abortion bans on fertility rates in the US
This repository includes replication code for "National and state-specific estimates of the unequal impacts of abortion bans on fertility in the US" (Bell et al)

- The data we analyzed was pulled from CDC Wonder and can be found in `data/fertility_data.csv`

## Model Fit
You can fit the model by running the python file `run_bimonthly.py`. The following flags can be set at the bottom of this file in the `main` call:
- `disp_param`: the dispersion parameter for the negative binomial.  We use 1e-4.  A value of zero is equivalent to a Poisson distribution.  See paper appendix for discussion.
- `num_chains, num_samples, num_warmup`
- `sample_disp`: The supplied value of `disp_param` is ignored and we sample the disperion parameter using [a penalized complexity prior](https://dansblog.netlify.app/posts/2022-08-29-priors4/priors4.html).  Currently this does not work due to poor mixing / convergence issues.

