---
sort: 1
---

# Running Python in OpenFOAM with pybind11

In [Rodriguez and Cardiff (2022)](https://journal.openfoam.com/index.php/ofj/article/view/79), a general approach to run Python codes in OpenFOAM was introduced, based on the header-only library pybind11. A Python interpreter is embedded in OpenFOAM and interacted with. The conceptual flowchart of the approach is shown in the figure below.

<!-- In 2022, Rodriguez and Cardiff introduced an approach to run Python codes in OpenFOAM ([see paper](https://tinyurl.com/pybind11foam)), based on the header-only library pybind11. -->



<img src="/images/6steps.png" alt="6 steps to communicate Python and OpenFOAM">


Efficient data transfer is achieved by combining [_ctypes_](https://docs.python.org/3/library/ctypes.html), NumPy's built-in support for [_ctypes_](https://docs.python.org/3/library/ctypes.html) and OpenFOAM's `data` (or `cdata`) functions for OpenFOAM `Lists/Fields`. 


`pythonPal` hides the details related to `ctypes`, `NumPy` and `data` by offering higher-level methods to transfer data between OpenFOAM and Python and execute general Python code.