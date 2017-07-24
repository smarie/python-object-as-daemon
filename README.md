# python-object-as-daemon (pyoad)

Project page : [made with mkdocs](https://smarie.github.io/python-object-as-daemon/)

## What's new

* Doc now generated from markdown using [mkdocs](http://www.mkdocs.org/)

## Want to contribute ?

Contributions are welcome ! Simply fork this project on github, commit your contributions, and create pull requests.

Here is a non-exhaustive list of interesting open topics: https://github.com/smarie/python-object-as-daemon/issues

## Packaging

This project uses `setuptools_scm` to synchronise the version number. Therefore the following command should be used for development snapshots as well as official releases: 

```bash
python setup.py egg_info bdist_wheel rotate -m.whl -k3
```
