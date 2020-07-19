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