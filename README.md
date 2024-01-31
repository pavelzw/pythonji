# 🐍 - Write Python with Emojis

![License][license-badge]
[![Build Status][build-badge]][build]
[![conda-forge][conda-forge-badge]][conda-forge]
[![pypi-version][pypi-badge]][pypi]
[![python-version][python-version-badge]][pypi]

[license-badge]: https://img.shields.io/github/license/pavelzw/pythonji-2?style=flat-square
[build-badge]: https://img.shields.io/github/actions/workflow/status/pavelzw/pythonji-2/ci.yml?style=flat-square&branch=main
[build]: https://github.com/pavelzw/pythonji-2/actions/
[conda-forge]: https://prefix.dev/channels/conda-forge/packages/pythonji-2
[conda-forge-badge]: https://img.shields.io/conda/pn/conda-forge/pythonji-2?style=flat-square&logoColor=white&logo=conda-forge
[pypi]: https://pypi.org/project/pythonji-2
[pypi-badge]: https://img.shields.io/pypi/v/pythonji-2.svg?style=flat-square&logo=pypi&logoColor=white
[python-version-badge]: https://img.shields.io/pypi/pyversions/pythonji-2?style=flat-square&logoColor=white&logo=python

> [!NOTE]
> This is a fork of [gahjelle/pythonji](https://github.com/gahjelle/pythonji) because it's not maintained anymore.

Write Python code using emojis 🐍

![Example of running 🐍](pythonji.gif)

## Inspiration

[Marc Garcia](http://datapythonista.github.io/) gave a wonderful [lightning talk](https://www.youtube.com/watch?v=Wtm7Iy-wEUI&t=52m43s) at [EuroSciPy 2018 in Trento](https://www.euroscipy.org/2018/), where he pointed out some obvious [deficiencies](https://github.com/python/cpython/pull/1686) in Python's handling of unicode. For instance, code like the following is not supported:

```python
import pandas as 🐼
```

## Installation

🐍 is available on [PyPI][pypi] and [conda-forge][conda-forge]. Install it with `pip` or `conda` or `pixi`:

```bash
pip install pythonji-2
conda install -c conda-forge pythonji-2
pixi add pythonji-2
```

## Using 🐍

🐍 installs as `pythonji`. 🐍 code files have the suffix `.🐍`. You can run a 🐍 code file as follows:

```bash
pythonji file.🐍
```

## Example

Save the following code to the file `🐼.🐍`:

```python
import pandas as 🐼
from numpy import random as 🔀

# Define a dataframe and print it to the console
📋 = 🐼.DataFrame(
    {
        "😀": ["🐼", "🐍", "🦁"],
        "🏷️": ["Panda", "Python", "Lion"],
        "💯": 🔀.randint(2, 5, size=3),
    },
).set_index("😀")
print(📋)

# Do some arithmetic with the dataframe
🔤 = f" Pythonji {' '.join(📋.index)}"
🔢 = 📋.loc["🐍", "💯"] + 📋.loc["🐼", "💯"]
print(🔤 * 🔢)
```

You can run the code as follows:

```bash
$ pythonji 🐼.🐍 
        🏷  💯
😀           
🐼   Panda  2
🐍  Python  2
🦁    Lion  4
 Pythonji 🐼 🐍 🦁 Pythonji 🐼 🐍 🦁 Pythonji 🐼 🐍 🦁 Pythonji 🐼 🐍 🦁
```

## Limitations

- 🐍 currently only handles single script files. It can import any regular Python module, but unfortunately not 🐍 modules.
- Sadly, `pip` does not currently handle unicode command names. Ideally, we want the executable to be named `🐍` instead of `pythonji`.
- [Black](https://black.readthedocs.io) unfortunately can not handle 🐍 code. Does anybody want to contribute to ⬛, a formatter for 🐍?
