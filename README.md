# virtualenv-for-ipython-notebook
This repository serves as a tutorial to set up the virtualenv and virtualenvwrapper for ipython notebook.

1. First, let's install the virtualenvwrapper:
```
sudo pip install virtualenvwrapper
```

2. Set variables:
```
cd $HOME
vim .bash_profile
```
Add these lines to the .bash_profile, save, and quit:
```
export WORKON_HOME="$HOME/.virtualenvs"
source usr/local/bin/virtualenvwrapper.sh
```
Then just source the .bashrc file:
```
source .bashrc
```

3. Now let's create a virtual environment called *yogurt*:
```
mkvirtualenv yogurt
```
Note that it already activated the environment for you. Then you can just
```
cdvirtualenv
```
install whatever package you want.

4. The last step, we want to actually use this environment in an ipython notebook. The only thing we need to do is to create a kernel linked to this environment.
```
pip install ipykernel
python -m ipykernel install --user --name=yogurt
```
Then you should be able to switch kernels in the notebook. Just go to ipython notebook menu, click *Kernel -> Change kernel* and change the kernel to *yogurt*. (If you cannot see this option, just restart the notebook.)
