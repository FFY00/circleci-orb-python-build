# circleci-orb-python-build

Builds Python sdists and wheels for packages using the new
[python-build](https://github.com/FFY00/python-build) CLI tool.

The `circleci/python` orb uses the old `setup.py` process to build packages,
which is deprecated and not compatible with
[PEP 517](https://www.python.org/dev/peps/pep-0517/). Newer projects that adopt
PEP 517 cannot use `circleci/python`'s `dist` command, hence the need for this orb.

Example:
```yaml
version: 2.1

orbs:
  python-build: ffy00/python-build@0.0.1

jobs:
  build:
    docker:
      - image: circleci/python:3.8
    steps:
      - checkout
      - python-build/build
```
