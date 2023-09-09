To build the `pex` I just run `pants package ::`. I'm running `python 3.10.8` via `pyenv`. To setup `Jupyter` I ran

```
python3.10 -m pip install notebook==7.0.3
python3.10 -m pip install ipykernel==6.25.2

```

To create a kernel for `Jupyter` I ran

```
python3.10 -m ipykernel install --user --name python3.10.8
```

To start `jupyter` I ran `python3.10 -m notebook`. I also made sure to select the `python3.10.8` kernel in the `Jupyter` notebook.

Visitng the URL that pops up in the console and trying to execute the notebook I get the following error:

```
---------------------------------------------------------------------------
ModuleNotFoundError                       Traceback (most recent call last)
Cell In[2], line 1
----> 1 import flask

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/flask/__init__.py:1
----> 1 from . import json as json
      2 from .app import Flask as Flask
      3 from .app import Request as Request

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/flask/json/__init__.py:6
      3 import json as _json
      4 import typing as t
----> 6 from ..globals import current_app
      7 from .provider import _default
      9 if t.TYPE_CHECKING:  # pragma: no cover

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/flask/globals.py:6
      3 import typing as t
      4 from contextvars import ContextVar
----> 6 from werkzeug.local import LocalProxy
      8 if t.TYPE_CHECKING:  # pragma: no cover
      9     from .app import Flask

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/werkzeug/__init__.py:2
      1 from .serving import run_simple as run_simple
----> 2 from .test import Client as Client
      3 from .wrappers import Request as Request
      4 from .wrappers import Response as Response

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/werkzeug/test.py:43
     41 from .urls import _urlencode
     42 from .urls import iri_to_uri
---> 43 from .utils import cached_property
     44 from .utils import get_content_type
     45 from .wrappers.request import Request

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/werkzeug/utils.py:24
     22 from .exceptions import NotFound
     23 from .exceptions import RequestedRangeNotSatisfiable
---> 24 from .security import safe_join
     25 from .wsgi import wrap_file
     27 if t.TYPE_CHECKING:

File ~/.pex/venvs/6c8eaec5b07b6fe5d8c257cd72d1297dfafdfc8e/779eb2cc0ca9e2fdd204774cbc41848e4e7c5055/lib/python3.10/site-packages/werkzeug/security.py:7
      5 import os
      6 import posixpath
----> 7 import secrets
      8 import warnings
     10 SALT_CHARS = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"

ModuleNotFoundError: No module named 'secrets'
```