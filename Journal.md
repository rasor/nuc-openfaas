### Folders

* \4ItProjs\projs-hathon\2019-Ng-PreFix 
* \4ItProjs\projs-hathon\2019-Py-NuCypher
https://github.com/nucypher/nucypher
* \p4Projs\2019-NuCypher
* (\4ItProjs\projs-openfaas)

### NuCypher Quickstart

* [Nucypher Quickstart](https://nucypher.readthedocs.io/en/latest/guides/quickstart.html)
* [Finnegan’s Wake Demo](https://nucypher.readthedocs.io/en/latest/demos/finnegans_wake_demo.html)
* [Installation Guide](https://nucypher.readthedocs.io/en/latest/guides/installation_guide.html)

New strategy:  
Opposed to building finnegans_wake_demo in dev, then just use nucypher lib.  

* Store py code as OpenFaaS templates on github
* Code uses the py nucypher lib
* Code deployed as OpenFaaS funcs
* Ng cli uses them
* OpenFaaS quick start: [OpenFaaS on Windows Devbox](https://rasor.github.io/openfaas-on-windows-devbox.html)

```bash
# Verify Faas CLI is responding
faas-cli version
# version: 0.8.6

# We want more funcs here
faas-cli list
# Function                        Invocations     Replicas
# faas-py-test1                   0               1
# figlet                          0               1

# Find a place for your code
cd .\2019-Py-NuCypher
md nuc-openfaas
cd nuc-openfaas
# Create a python project
faas-cli new nucypher-test1 --lang python3
# Function created in folder: nucypher-test1
# Stack file written: nucypher-test1.yml

# Cleanup - Delete all folders under \template\ except for python3

```

-------------------------------

### finnegans_wake_demo

Trying out finnegans_wake_demo in dev mode on Windows - got into problems ....

Following (windows re-written verrsion of) \nucypher\examples\finnegans_wake_demo\README.md

From Git Bash

```bash
# /2019-Py-NuCypher
git clone https://github.com/nucypher/nucypher
cd nucypher
git checkout cone  # We need a federated branch which isn't using blockchain

### Download the Book! - the secret data to share
cd .\examples\finnegans_wake_demo
./download_finnegans_wake.sh
# ./download_finnegans_wake.sh: line 4: wget: command not found
# hmm no wget - download file manually from 
# https://github.com/nucypher/nucypher-kms/files/1765576/finnegans-wake.txt
```

From CMD

```bash
### Install Nucypher

pip3 install pipenv # if not yet installed
# checkout pipenv guide: https://realpython.com/pipenv-guide/
pipenv install --dev --three --skip-lock --pre
# Creating a virtualenv for this project▒
# Pipfile: C:\Users\yourname\E-Toshiba\4ItProjs\projs-hathon\2019-Py-NuCypher\nucypher\Pipfile
# Using C:/Program Files (x86)/Python36-32/python.exe (3.6.4) to create virtualenv▒
# [  ==] Creating virtual environment...Using base prefix 'C:\\Program Files (x86)\\Python36-32'
# New python executable in C:\Users\yourname\.virtualenvs\nucypher-n89rVxud\Scripts\python.exe
# Installing setuptools, pip, wheel...
# done.
# Running virtualenv with interpreter C:/Program Files (x86)/Python36-32/python.exe
# Successfully created virtual environment!
# Virtualenv location: C:\Users\yourname\.virtualenvs\nucypher-n89rVxud
# Installing dependencies from Pipfile▒
# An error occurred while installing pytest==4.0.2! Will try again.
# An error occurred while installing pytest-xdist! Will try again.
# An error occurred while installing pytest-twisted! Will try again.
# An error occurred while installing mypy! Will try again.
# An error occurred while installing ansible! Will try again.
# An error occurred while installing sphinx! Will try again.
# An error occurred while installing -e .! Will try again.
# An error occurred while installing py-evm==0.2.0a39! Will try again.
# Installing initially failed dependencies▒
# To activate this project's virtualenv, run pipenv shell.
# Alternatively, run a command inside the virtualenv with pipenv run.

# Where is virtualenv?
pipenv --venv
# C:\Users\yourname\.virtualenvs\nucypher-n89rVxud

# Working directory?
pipenv --where
# C:\Users\yourname\2019-Py-NuCypher\nucypher

# What is installed now?
pipenv graph
# pipenv graph --reverse # for seeing lowest dependencies first
# ....
# maya==0.6.1
# ....
# umbral==0.1.3a0
# ....

# Start virtualenv (from .env file) in this shell??
pipenv shell
# Launching subshell in virtual environment…
# (nucypher-n89rVxud) C:\Users\yourname\2019-Py-NuCypher\nucypher>

# We are running in the virtualenv now - prompt prefix shows that (nucypher-n89rVxud) 

### Run
cd .\examples\finnegans_wake_demo
# Manually running content of
# py -3 finnegans-wake-concise-demo.py
py -3
# Python 3.6.4 (v3.6.4:d48eceb, Dec 19 2017, 06:04:45) [MSC v.1900 32 bit (Intel)] on win32
# Type "help", "copyright", "credits" or "license" for more information.
```

Entering into py -3 prompt:  
finnegans-wake-concise-demo.py:

```python
import os
import datetime
import maya
# ModuleNotFoundError: No module named 'maya'

exit()
```
``` bash
# exit the virtualenv - back to the normal prompt
exit

```

