# importDadiResults

## About

An R function to extract data from multiple [∂a∂i](https://bitbucket.org/gutenkunstlab/dadi) (aka dadi, Diffusion Approximations for Demographic Inference) output files. Parses, cleans, and aggregates dadi results, calculates statistical metrics, and outputs a formatted table of comparative results. 

## Features

- Imports multiple dadi output files.
- Extracts and parses data, 
- Handles broken rows and unwanted characters.
- Identifies and extract parameters based on a given parameter list.
- Computes AIC and AICc values for model comparison.
- Outputs a data frame with processed results.

Requires [dplyr](https://cran.r-project.org/web/packages/dplyr/index.html). Built with R 4.3

## Inputs

- `filenames` (character vector): directory of dadi results files.
- `param.list` (list): models and parameter names
- `n.list` (list): sample sizes for each dataset (required for AICc calculation)
- `verbose` (boolean): print detailed information during processing if TRUE. Default is FALSE.

## Outputs

A data.frame with a row for each dadi model, and the following columns:

- `start`: initial value for each run
- `posterior`: estimates for parameters
- `loglikelihood`: log-likelihood value
- `theta`: Estimated theta (4Ne​μ)
- `prior`: parameter priors
- `upper`: Estiamted upper bounds
- `lower`: Estimated lower bounds
- `pts`: number of grid points used
- `flnms`: File names
- `AIC`: Akaike Information Criterion
- `AICc`: AIC corrected for small sample sizes.


## Citations

Gutenkunst, R., Hernandez, R., Williamson, S. et al. Diffusion Approximations for Demographic Inference: DaDi. Nat Prec (2010). [10.1038/npre.2010.4594.1](https://doi.org/10.1038/npre.2010.4594.1)
