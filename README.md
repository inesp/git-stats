# git-stats


## Set up

Set up virtualenv for Python3.6:
```bash
virtualenv -p /usr/bin/python3 env
```
Activate the virtualenv:
```bash
source env/bin/activate
```
Install the requirements
```bash
pip install -r requirements.txt
```

## Thought process

Clone repository.

Set up virtualenv for Python3.6:
```bash
virtualenv -p /usr/bin/python3 env
```
This creates an `env`-folder to where is saves all dependencies.
Activate the virtualenv:
```bash
source env/bin/activate
```
The name of the current virtual environment will now appear on the left of the 
prompt (e.g. (env)Your-Computer:your_project UserName$) to let you know that 
it’s active. From now on, any package that you install using pip will be 
placed in the my_project folder, isolated from the global Python installation.

When you're done with the virtual env call:
```bash
deactivate
```

To delete a virtual environment, just delete its folder. 
(In this case, it would be `rm -rf env`.)

While developing you can call `pip install <whatever>` and after that from time
to time you shouold call:
```bash
pip freeze > requirements.txt
```
This creates the requirements.txt with a list of requirements.
But it seems the freeze puts a lot of items into the file. If I call 
`pip install request` it fills the requirements.txt file with every 
sub-package the request needs. This might be redundant. Or not :)

You should not commit the virtualenv to GIT, but you shouold commit the 
requirements.txt.

When cloning the project to anew you should call:
```bash
pip install -r requirements.txt
```
