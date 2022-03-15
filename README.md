# Welcome to `pymc-experimental`

As PyMC continues to mature and expand its functionality to accomodate more domains of application, we increasingly see cutting-edge methodologies, highly specialized statistical distributions, and complex models appear.
While this adds to the functinoality and relevance of the project, it can also introduce instability and impose a burden on testing and quality control.
To reduce the burden on the main `pymc` repository, this `pymc-experimental` respository can become the aggregator & testing ground for new additions to PyMC.
This may include unusual probability distribitions, advanced model fitting algorithms, or any code that may be inappropriate to include in the `pymc` repository, but may want to be made available to users.

The `pymc-experimental` repository can be understood as the first step in the PyMC development pipeline, where all novel code is introduced until it is obvious that it belongs in the main repository.
We hope that this improves the stability and streamlines the testing overhead of the `pymc` respository.

`pymc-experimental` would be designed to mirror the namespaces in `pymc` to make usage and migration as easy as possible.
For example, a `ParabolicFractal` distribution could be used analogously to those in `pymc`:

```python
import pymc as pm
import pymc_experimental as pmx

with pm.Model():

    alpha = pmx.ParabolicFractal('alpha', b=1, c=1)
    
    ...

```

## Questions

### What belongs in `pymc-experimental`?

- newly-implemented statistical methods, for example diagnostics or step methods
- distributions that are tricky to sample from or test
- infrequently-used fitting methods or distributions
- any code that requires additional optimization before it can be used in practice


### What does not belong in `pymc-experimental`?
- Case studies
- Implementations that cannot be applied generically


### Should there be more than one add-on repository?

Since there is a lot of code that we may not want in the main repository, does it make sense to have more than one additional repository?
For exmaple, `pymc-experimental` may just include methods that are not fully developed, tested and trusted, while code that is known to work well and has adequate test coverage could reside in a `pymc-extras` (or similar) repository.


### Unanswered questions & ToDos
This project is still young and many things have not been answered or implemented.
Please get involved!

* What are guidlines for organizing submodules?
  * Proposal: No default imports of WIP/unstable submodules. By importing manually we can avoid breaking the package if a submodule breaks, for example because of an updated dependency.
* How can we minimize the additional burden of additional project repositories?
* ToDo: Setting up a basic CI pipeline


