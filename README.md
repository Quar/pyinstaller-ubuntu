# Dockerized PyInstaller on Ubuntu


## Motivation

PyInstaller is handy in packing Python scripts along with its dependencies into
an uber-file. However,

> PyInstaller does not bundle `libc` (the C standard library, usually `glibc`,
the GNU version) with the app. [1]

This makes bundle for Ubuntu a bit harder, especially due to the tendency of Ubuntu
for adopting new C standard library while a bit backwards in adopting newer version
of Python.

Therefore, to bundle a Python app for an Ubuntu distribution, the easiest solution
is to mount the Python app into a Dockerized Ubuntu container, using PyInstaller
to bundle and export, then deliver.


## To Use

The mounting point `/code` has been created, use it like:

```bash
docker run -it --rm -v "$PWD:/code" quar/pyinstaller-ubuntu:18.04
```


[1]: https://pyinstaller.readthedocs.io/en/stable/usage.html#making-gnu-linux-apps-forward-compatible

## Tags:

| Docker Image                  | Ubuntu Version | Python Version |
| :-----:                       | :----:         | :----:         |
| quar/pyinstaller-ubuntu:18.04 | 18.04          | 3.6.9          |
