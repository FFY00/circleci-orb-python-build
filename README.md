# circleci-orb-python-build

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