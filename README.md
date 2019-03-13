python-ubi-config
==================

A Python library for reading UBI configurations

[![Build Status](https://travis-ci.org/release-engineering/ubi-config.svg?branch=master)](https://travis-ci.org/release-engineering/ubi-config)
[![Coverage Status](https://coveralls.io/repos/github/release-engineering/ubi-config/badge.svg?branch=master)](https://coveralls.io/github/release-engineering/ubi-config?branch=master)

- [Source](https://github.com/release-engineering/ubi-config)
- [Documentation](https://release-engineering.github.io/ubi-config/)
- [PyPI](https://pypi.org/project/ubi-config)

Installation
------------

Install the `ubi-config` package from PyPI.

```
pip install ubi-config
```


Usage Example
-------------
When there is `DEFAULT_UBI_REPO` set, user can load the config by passing the config file
name to `get_loader().load()`

```python
from ubi_config import get_loader

config = get_loader().load('rhel-8-for-x86_64-appstream')
# config has been validated and is now a Python object with relevant properties
package_whitelist = config.packages.whitelist
print package_whitelist
```
Or, get all config files from the repo:
```python

from ubi_config import get_loader

configs = get_loader().load_all()
# returns a list of UbiConfig objects
```
Or, user can also load the config from local file:
```python
from ubi_config import get_loader

config = get_loader(local=True).load('/path/to/rhel-8-for-x86_64-appstream.yaml')
```

License
-------
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.
