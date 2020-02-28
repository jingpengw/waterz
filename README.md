[![Build Status](https://travis-ci.org/jingpengw/waterz.svg?branch=master)](https://travis-ci.org/jingpengw/waterz)
[![PyPI version](https://badge.fury.io/py/waterzed.svg)](https://badge.fury.io/py/waterzed)

<!--
    the coerage is not working on c++ code, so the coverage is 0 now!
    [![Coverage Status](https://coveralls.io/repos/github/jingpengw/waterz/badge.svg?branch=master)](https://coveralls.io/github/jingpengw/waterz?branch=master)
-->

# waterz

Pronounced *water-zed*. A simple watershed and region agglomeration library for
affinity graphs.

Based on the watershed implementation of [Aleksandar Zlateski](https://bitbucket.org/poozh/watershed) and [Chandan Singh](https://github.com/TuragaLab/zwatershed).

# Installation

Install c++ dependencies:
```
sudo apt install libboost-dev
```

Install from pipy
```
pip install waterzed
```

install manually
```
pip install -r requirements.txt
python setup.py install
```

# Usage

```
import waterz
import numpy as np

# affinities is a [3,depth,height,width] numpy array of float32
affinities = ...

thresholds = [0, 100, 200]

segmentations = waterz.agglomerate(affinities, thresholds)
```

# Development
## Release to pypi
We use travis to create release

upgrade the version number in the `setup.py` file, then
```
git tag -a v1.4 -m "my version 1.4"
git commit -a -m "my comments"
git push
```
the travis build system will get a `TRAVIS_TAG` variable, and triger the `twine upload` command.
