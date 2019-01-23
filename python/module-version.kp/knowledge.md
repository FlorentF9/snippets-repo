---
title: Python module version
authors:
- FlorentF9
tags:
- python
created_at: 2019-01-23 00:00:00
updated_at: 2019-01-23 18:00:39.944818
tldr: Finding out the version of a Python module.
---

### Python module version

This commands prints all modules installed via pip with their versions. A particular module can be found using grep:

```shell
$ pip freeze | grep module
```

For most modules, version number is available in a variable called `__version__`.

```shell
$ python -c "import module; print(module.__version__)"
```

For example:


```python
import numpy
print(numpy.__version__)
```
    1.14.2