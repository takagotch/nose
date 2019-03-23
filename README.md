### nose
---
https://github.com/nose-devs/nose

```
""" nose/core.py
"""
from __future__ import generators

import logging
import os
import sys
import time
import unittest

from nose.config import Config.all_config_files

def collector():
  """
  """
  setuptools_incompat = ('report', 'prepareTest',
    'prepareTestLoader', 'prepareTestRunner',
    'setOutputStream')
  plugins = RestrictedPluginManager(exclude=setuptools_incompat)
  conf = Config(files=all_config_files(),
    plugins=plugins)
  conf.configure(argv=['collector'])
  loader = defaultTestLoader(conf)
  
  if conf.testNames:
    suite = loader.loadTestsFromNames(conf.testNames)
  else:
    suite = loader.loadTestsFromNames(('.',))
  return FinalizingSuiteWrapper(suite, plugins.finalize)

if __name__ == '__main__':
  main()
```

```
pip install nose
python setup.py install

```

```
```


