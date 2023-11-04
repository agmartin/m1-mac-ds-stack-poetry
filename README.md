# M1 Mac Data Science Stack Using Poetry

This is a repo for getting a Python Data Science stack set up
on Apple Silicon Macs using `pyenv` and `poetry`.


I'm putting this out there because it has been a huge pain in the ass in the past.

This seems to be working for now. Let's see what happens the next
time I update macOS.

Starting with a brand new mac, install Xcode tools to begin with.


`xcode-select --install` and accept the agreement in the popup box.

## Install Homebrew

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Install Python build dependencies:

`brew install openssl readline sqlite3 xz zlib tcl-tk`


## Install pyenv pyenv-virtualenv
`brew install pyenv pyenv-virtualenv`

## Activate pyenv in your shell

`echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc`
`echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc`
`echo 'eval "$(pyenv init -)"' >> ~/.zshrc`
`echo 'if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi'`

## Restart your shell

`exec "$SHELL"`

## Now you can begin to use pyenv

`pyenv install 3.11.6`

This will compile Python on your machine and make it available.

## Create a virtual environment

`pyenv virtualenv 3.11.6 <name>`


## Clone this repo and cd to it

`git clone git@github.com:agmartin/m1-mac-ds-stack-poetry && cd m1_ds_stack_poetry`

`pyenv local <name>`


## Set up poetry to manage your dependencies based on your pyenv setup
## Do not use homebrew to install poetry globally. It has a dependency on Python itself and it WILL break when you update && upgrade homebrew!!! Install poetry locally inside pyenv instead!


`pip install --upgrade pip` # get the latest version of pip\
`pip install poetry`\
`poetry env use python` # tell poetry to use your pyenv defined python install

Finally we can install the project.

`poetry install`




