# Changelog

### 2.1.4 - improved packaging

 - packaging improvements: set the "universal wheel" flag to 1, and cleaned up the `setup.py`. In particular removed dependency to `six` for setup and added `py.typed` file, as well as set the `zip_safe` flag to False. Removed tests folder from package. Fixes [#16](https://github.com/smarie/python-spawny/issues/16)

### 2.1.3 - Added `pyproject.toml`

Added `pyproject.toml`.

### 2.1.2 - Added `__version__` attribute

Added `__version__` attribute at package level.

### 2.1.1 - Fixed issue with python 2

Fixed [#15](https://github.com/smarie/python-spawny/issues/15).

### 2.1.0 - Better protection against exceptions in the daemon

Now exceptions happening on the daemon side always result in a corresponding message being sent to the client, even if the exception itself is not picklable. Fixes [#14](https://github.com/smarie/python-spawny/issues/14).

### 2.0.2 - bugfix

Fixed error with typing module on some 3.7 distributions. Fixed [#13](https://github.com/smarie/python-spawny/issues/13).

### 2.0.1 - Support for scripts, new name: `spawny`, support for python 2.

**General:**

 - The package is now named `spawny`. Let's hope that it will be a more intuitive name for users :)

 - Added support for python 2. Fixed [#4](https://github.com/smarie/python-spawny/issues/4)

**API:**

 - You can now execute an entire script or a module in the daemon, thanks to new `ScriptDefinition` and `ModuleDefinition`. A new `Definition` super type was created that is the parent of all definitions. 
 
 - `ObjectDaemonProxy` was renamed `DaemonProxy` because it now represents the proxy for the entire daemon, whatever it is, while new class `ObjectProxy` represents the proxy for a given object. Several `ObjectProxy` rely on the same `DaemonProxy` to communicate with the other process. Fixes [#2](https://github.com/smarie/python-spawny/issues/2) and [#7](https://github.com/smarie/python-spawny/issues/7). 

 - New high-level methods: `run_script`, `run_module`, `run_object`. These make the doc much easier to read and the package more intuitive to use.

**Other features:**

 - Now catching exceptions happening at initialization time, and reporting them in the caller. Fixed [#5](https://github.com/smarie/python-spawny/issues/5).

 - Fixed bug with python 2 ints not implementing rich comparison. Fixed [#12](https://github.com/smarie/python-spawny/issues/12)

### 1.0.2 - Better travis integration

 * added test reports generation
 * added automatic PyPI deployment

### 1.0.1 - Bugfix for linux and Travis integration

 * removed reference to PipeConnection in PEP484 annotation. fixes #1 (bug on Linux environments)
 * integrated in travis: tests, code coverage, doc generation

### 1.0.0 - First public working version
