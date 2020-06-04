# Python Essentials

## Versions

Ensure you have the latest pip, wheel, and virtualenv:

> python -m pip install --upgrade pip wheel setuptools virtualenv

## Kivy

Optionally create a new virtual environment for your Kivy project. Highly recommended:

First create the environment named kivy_venv in your current directory:

> python -m virtualenv kivy_venv

```
PS C:\Users\gsalas1\Documents\GitHub\grs-python-private\projects\network-programmer\venv>
PS C:\Users\gsalas1\Documents\GitHub\grs-python-private\projects\network-programmer\venv>  python -m virtualenv kivy_venv
Using base prefix 'C:\\Users\\gsalas1\\AppData\\Local\\Programs\\Python\\Python37-32'
New python executable in C:\Users\gsalas1\Documents\GitHub\grs-python-private\projects\network-programmer\venv\kivy_venv\Scripts\python.exe
Installing setuptools, pip, wheel...
done.
```

Activate the virtual environment. You’ll have to do this step from the current directory every time you start a new terminal. On windows CMD do:

> kivy_venv\Scripts\activate

If you’re in a bash terminal, instead do:

> source kivy_venv/Scripts/activate

Install the dependencies (skip gstreamer (~120MB) if not needed, see Kivy’s dependencies). If you are upgrading Kivy, see Updating Kivy from a previous release:

> python -m pip install docutils pygments pypiwin32 kivy_deps.sdl2==0.1.* kivy_deps.glew==0.1.*

> python -m pip install kivy_deps.gstreamer==0.1.*

### Note

If you encounter a MemoryError while installing, add after pip install the –no-cache-dir option.

For Python 3.5+, you can also use the angle backend instead of glew. This can be installed with:

> python -m pip install kivy_deps.angle==0.1.*

### Warning

When installing, pin kivy’s dependencies to the specific version that was released on pypi when your kivy version was released, like above. Otherwise you may get an incompatible dependency when it is updated in the future.
