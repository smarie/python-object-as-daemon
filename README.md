# python-object-as-daemon (pyoad)

[![Build Status](https://travis-ci.org/smarie/python-object-as-daemon.svg?branch=master)](https://travis-ci.org/smarie/python-object-as-daemon) [![Tests Status](https://smarie.github.io/python-object-as-daemon/junit/junit-badge.svg?dummy=8484744)](https://smarie.github.io/python-object-as-daemon/junit/report.html) [![codecov](https://codecov.io/gh/smarie/python-object-as-daemon/branch/master/graph/badge.svg)](https://codecov.io/gh/smarie/python-object-as-daemon) [![Documentation](https://img.shields.io/badge/docs-latest-blue.svg)](https://smarie.github.io/python-object-as-daemon/) [![PyPI](https://img.shields.io/badge/PyPI-pyoad-blue.svg)](https://pypi.python.org/pypi/pyoad/)


Project page : [https://smarie.github.io/python-object-as-daemon/](https://smarie.github.io/python-object-as-daemon/)

## What's new

* Travis and codecov integration
* Doc now generated from markdown using [mkdocs](http://www.mkdocs.org/)
* most special methods are now correctly proxified
* object instance can now be created on either side (main process or daemon)

## Want to contribute ?

Contributions are welcome ! Simply fork this project on github, commit your contributions, and create pull requests.

Here is a non-exhaustive list of interesting open topics: [https://github.com/smarie/python-object-as-daemon/issues](https://github.com/smarie/python-object-as-daemon/issues)

## Running the tests

This project uses `pytest`. 

```bash
pytest -v pyoad/tests/
```

You may need to install requirements for setup beforehand, using 

```bash
pip install -r ci_tools/requirements-test.txt
```

## Packaging

This project uses `setuptools_scm` to synchronise the version number. Therefore the following command should be used for development snapshots as well as official releases: 

```bash
python setup.py egg_info bdist_wheel rotate -m.whl -k3
```

You may need to install requirements for setup beforehand, using 

```bash
pip install -r ci_tools/requirements-setup.txt
```

## Generating the documentation page

This project uses `mkdocs` to generate its documentation page. Therefore building a local copy of the doc page may be done using:

```bash
mkdocs build
```

You may need to install requirements for doc beforehand, using 

```bash
pip install -r ci_tools/requirements-doc.txt
```

## Generating the test reports

The following commands generate the html test report and the associated badge. 

```bash
pytest --junitxml=junit.xml -v autoclass/tests/
ant -f ci_tools/generate-junit-html.xml
python ci_tools/generate-junit-badge.py
```

### PyPI Releasing memo

This project is now automatically deployed to PyPI when a tag is created. Anyway, for manual deployment we can use:

```bash
twine upload dist/* -r pypitest
twine upload dist/*
```
