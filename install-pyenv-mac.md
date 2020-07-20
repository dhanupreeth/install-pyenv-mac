## Installing and Uninstalling multiple Python versions using Pyenv - MAC

## Warnings
Not supposed remove any python versions from below path. 
```bash
# Those version of python are installed by Apple and the same will be used by MAC OS &
# other software to perform installation and dependencies, functions. 
# Deleting the python from these directories will crash the MAC OS and force to re-install it 

/usr/bin
system/Library
```
# Installation
## Homebrew [Install](https://brew.sh/)
```bash
# Command
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### To install Python 3:
```bash
brew install python
```
### To install Python 2:
```bash
brew install python@2
```
### Path and .bash_profile Settings
#### Path
```bash
echo $PATH # to display the PATH variables

/Users/USERNAME/.nvm/versions/node/v9.0.0/bin:/usr/local/opt/python@3.8/bin:/usr/local/opt/openssl@1.1/bin:/Users/USERNAME/.pyenv/shims:/Users/USERNAME/.rvm/gems/ruby-2.3.0/bin:/Users/USERNAME/.rvm/gems/ruby-2.3.0@global/bin:/Users/USERNAME/.rvm/rubies/ruby-2.3.0/bin:/Users/USERNAME/.rbenv/shims:/usr/local/opt/openssl/bin:/Users/USERNAME/.rbenv/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/go/bin:/Users/USERNAME/.rvm/bin
```
Open the .bash_profile and python settings for path 3.7 and to keep all the version but the bash want to open the particular version then add the below lines to the bottom of the .bash_profile. 
```bash
# Setting PATH for Python 3.7
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.7/bin:${PATH}"
export PATH
```
save and close the .bash_profile and to reload the .bash_profile. 
```bash
source ~/.bash_profile
```

### Installing pyenv
Pyenv is a homebrew packages, it allows you to install multiple version of python and you choose which version of python you should to use.
```bash
brew install pyenv 
```
### Installing two versions of python
```bash
pyenv install 3.5.0
pyenv install 3.7.0 
```
### Show which versions of python are installed
```bash
pyenv versions
  system
* 3.5.9 (set by /Users/USERNAME/.pyenv/version)
  3.6.0
```
Currently I have two python versions, which is listing and I'm using 3.5.9 is the global version of python in my machine

### Change the Pyenv Version Project Based
```bash
mkdir python-project
cd python-project
pyenv local 3.6.0
```
Inside the `python-project` directory having python version of 3.6.0, the but the global version of python is 3.5.9 which has asterisk
```bash
pyenv global 3.6.0 # Setting the python 3.6.0 is the global version
```

### Locate Python in Mac
```bash 
which -a python
```
#### Output
```bash
- /Users/USERNAME/.pyenv/shims/python
- /usr/bin/python
```
```bash
which -a python3
```
#### Output
```bash
- /usr/local/opt/python@3.8/bin/python3
- /Users/USERNAME/.pyenv/shims/python3
```
### Uninstalling Python
System Application folder 
```bash 
- /Applications
- /Library/Frameworks/Python.framework
- /usr/local/bin
```
Delete all versions of python that installed via python.org installer, enter these commands in terminal:

```bash
sudo rm -rf '/Applications/Python A.B' #replace A.B with the version number on the folder
sudo rm -rf /Library/Frameworks/Python.framework
sudo rm -rf /usr/local/bin/python
sudo rm -rf /usr/local/bin/python3
```
### Removing Python from Framework & Application Framework
To remove particular versions of python, you have to refer to the particular framework. 
The frameworks are installed in /Library/Frameworks/Python.framework and particular versions are found in /Library/Frameworks/Python.framework/Versions/A.B. 
So for example if you wanted to uninstall only version 3.5 but leave other versions you would enter the following commands in bash:
```bash
sudo rm -rf /Library/Frameworks/Python.framework/Versions/3.5
sudo rm -rf '/Applications/Python 3.5'
sudo rm -rf /usr/local/bin/python3
```
### Uninstalling using Homebrew
```bash
brew list | grep 'python'
brew uninstall -f python python@2
brew uninstall --ignore-dependencies python python@2
brew uninstall -f python python@2 gdal geos libspatialite libxml2 numpy
brew unlink python python@2 && brew link python python@2
```
### Uninstalling using pyenv
```bash
pyenv versions
  system
* 3.5.9 (set by /Users/USERNAME/.pyenv/version)
  3.6.0
pyenv uninstall 3.5.9
pyenv uninstall 3.6.0
```
