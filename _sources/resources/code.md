# Code

In this book the wearable data analysis will be performed using Python code. We will use a few existing Python toolboxes in the analysis, which are now described.

## WFDB Toolbox

Waveform Database (WFDB) is a set of file standards designed for reading and storing physiologic signal data, and associated annotations. Data on [PhysioNet](https://physionet.org/) are stored in WFDB format.

The WFDB Toolbox is a set of openly-licensed tools for reading, writing, and analysing WFDB data. It is available in [C](https://doi.org/10.13026/gjvw-1m31), [Matlab](https://archive.physionet.org/physiotools/matlab/wfdb-swig-matlab/new_version.shtml), and [Python](https://wfdb.readthedocs.io/en/stable/).

In this book we will use the [WFDB Python Package](https://wfdb.readthedocs.io/en/stable/), a library of tools for reading, writing, and processing physiological signals and annotations. 

The WFDB Python Package can be installed using:

```python
$ pip install wfdb
```

It will be imported using: `import wfdb`

_Sources: adapted from [https://wfdb.io/](https://wfdb.io/) and the WFDB Python Package [Readme](https://github.com/MIT-LCP/wfdb-python/blob/main/README.md)._

## Neurokit

[Neurokit](https://neuropsychology.github.io/NeuroKit/) is a 'Python Toolbox for Neurophysiological Signal Processing'. It includes functions for analysing ECG and PPG signals, such as algorithms for detecting beats in these signals.

Neurokit can be installed using:

```python
$ pip install neurokit2
```

It will be imported using: `import neurokit2 as nk`

_Source: adapted from [https://neuropsychology.github.io/NeuroKit/](https://neuropsychology.github.io/NeuroKit/) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)._

## Additional toolboxes

The following toolboxes are also used in this book:
- **_sys_**: an essential python package, imported using `import sys`
- **_scipy_**: the SciPy signal processing package, imported using `import scipy.signal as sp`
- **_matplotlib_**: a plotting package, imported using `from matplotlib import pyplot as plt`
- **_numpy_**: a package for scientific computing, imported using `import numpy as np`
- **_pandas_**: a package for data analysis, imported using `import pandas as pd`
- **_pprint_**: for printing Python data structures, imported using `from pprint import pprint`
- **_copy_**: to copy Python variables, imported using `import copy`