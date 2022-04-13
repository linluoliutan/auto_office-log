According to the output of the cmd, we should install the pillow, but the error occurs:
```
C:\python_package\Pillow-9.1.0>python setup.py install
running install
running bdist_egg
running egg_info
writing src\Pillow.egg-info\PKG-INFO
writing dependency_links to src\Pillow.egg-info\dependency_links.txt
writing requirements to src\Pillow.egg-info\requires.txt
writing top-level names to src\Pillow.egg-info\top_level.txt
reading manifest file 'src\Pillow.egg-info\SOURCES.txt'
reading manifest template 'MANIFEST.in'
warning: no files found matching '*.c'
warning: no files found matching '*.h'
warning: no files found matching '*.sh'
warning: no files found matching '*.txt'
warning: no previously-included files found matching '.appveyor.yml'
warning: no previously-included files found matching '.clang-format'
warning: no previously-included files found matching '.coveragerc'
warning: no previously-included files found matching '.editorconfig'
warning: no previously-included files found matching '.readthedocs.yml'
warning: no previously-included files found matching 'codecov.yml'
warning: no previously-included files matching '.git*' found anywhere in distrib
ution
warning: no previously-included files matching '*.pyc' found anywhere in distrib
ution
warning: no previously-included files matching '*.so' found anywhere in distribu
tion
no previously-included directories found matching '.ci'
writing manifest file 'src\Pillow.egg-info\SOURCES.txt'
installing library code to build\bdist.win32\egg
running install_lib
running build_py
running build_ext


The headers or library files could not be found for zlib,
a required dependency when compiling Pillow from source.

Please see the install instructions at:
   https://pillow.readthedocs.io/en/latest/installation.html

Traceback (most recent call last):
  File "setup.py", line 996, in <module>
    zip_safe=not (debug_build() or PLATFORM_MINGW),
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\__init__.py",
line 145, in setup
    return distutils.core.setup(**attrs)
  File "C:\Program Files\Python37-32\lib\distutils\core.py", line 148, in setup
    dist.run_commands()
  File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 966, in run_co
mmands
    self.run_command(cmd)
  File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
mmand
    cmd_obj.run()
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
l.py", line 67, in run
    self.do_egg_install()
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
l.py", line 109, in do_egg_install
    self.run_command('bdist_egg')
  File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
mand
    self.distribution.run_command(command)
  File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
mmand
    cmd_obj.run()
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\bdist_
egg.py", line 172, in run
    cmd = self.call_command('install_lib', warn_dir=0)
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\bdist_
egg.py", line 158, in call_command
    self.run_command(cmdname)
  File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
mand
    self.distribution.run_command(command)
  File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
mmand
    cmd_obj.run()
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
l_lib.py", line 11, in run
    self.build()
  File "C:\Program Files\Python37-32\lib\distutils\command\install_lib.py", line
 107, in build
    self.run_command('build_ext')
  File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
mand
    self.distribution.run_command(command)
  File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
mmand
    cmd_obj.run()
  File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\build_
ext.py", line 84, in run
    _build_ext.run(self)
  File "C:\Program Files\Python37-32\lib\distutils\command\build_ext.py", line 3
40, in run
    self.build_extensions()
  File "setup.py", line 804, in build_extensions
    raise RequiredDependencyException(f)
__main__.RequiredDependencyException: zlib

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "setup.py", line 1009, in <module>
    raise RequiredDependencyException(msg)
__main__.RequiredDependencyException:

The headers or library files could not be found for zlib,
a required dependency when compiling Pillow from source.

Please see the install instructions at:
   https://pillow.readthedocs.io/en/latest/installation.html
```

To solve the problem, I download and install the zlib, which is a compression tool for modern multi-core machines written in Go.

It does not work.

then visit the [instructions](https://pillow.readthedocs.io/en/latest/installation.html)

> zlib provides access to compressed PNGs
> Starting with Pillow 3.0.0, zlib is required by default, but may be disabled with the --disable-zlib flag.

> Building on Windows
> We recommend you use prebuilt wheels from PyPI. If you wish to compile Pillow manually, you can use the build scripts in the winbuild directory used for CI testing and development. These scripts require Visual Studio 2017 or newer and NASM.

> Building on Windows using MSYS2/MinGW
> To build Pillow using MSYS2, make sure you run the MSYS2 MinGW 32-bit or MSYS2 MinGW 64-bit console, not MSYS2 directly.

> The following instructions target the 64-bit build, for 32-bit replace all occurrences of mingw-w64-x86_64- with mingw-w64-i686-.

> Make sure you have Python and GCC installed:
> ......
> Operating system Tested Python versions Latest tested Pillow version Tested processors
> Windows 7 Professional 3.7 7.0.0 x86,x86-64

Considering that the version tested is 7, so have a try.
Unluckily, it still fails.


### 0413
Try again, to help remember things day before yesterday.

- pyautogui
   ```
   C:\python_package\PyAutoGUI-0.9.53\PyAutoGUI-0.9.53>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing PyAutoGUI.egg-info\PKG-INFO
   writing dependency_links to PyAutoGUI.egg-info\dependency_links.txt
   writing requirements to PyAutoGUI.egg-info\requires.txt
   writing top-level names to PyAutoGUI.egg-info\top_level.txt
   reading manifest file 'PyAutoGUI.egg-info\SOURCES.txt'
   reading manifest template 'MANIFEST.in'
   writing manifest file 'PyAutoGUI.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pyautogui
   copying build\lib\pyautogui\_pyautogui_java.py -> build\bdist.win32\egg\pyautogu
   i
   copying build\lib\pyautogui\_pyautogui_osx.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\_pyautogui_win.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\_pyautogui_x11.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\__init__.py -> build\bdist.win32\egg\pyautogui
   copying build\lib\pyautogui\__main__.py -> build\bdist.win32\egg\pyautogui
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_java.py to _pyautogui_
   java.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_osx.py to _pyautogui_o
   sx.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_win.py to _pyautogui_w
   in.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_x11.py to _pyautogui_x
   11.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\__init__.py to __init__.cpython-3
   7.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\__main__.py to __main__.cpython-3
   7.pyc
   creating build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\dependency_links.txt -> build\bdist.win32\egg\EGG-INF
   O
   copying PyAutoGUI.egg-info\requires.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO
   zip_safe flag not set; analyzing archive contents...
   creating 'dist\PyAutoGUI-0.9.53-py3.7.egg' and adding 'build\bdist.win32\egg' to
    it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyAutoGUI-0.9.53-py3.7.egg
   Removing c:\program files\python37-32\lib\site-packages\PyAutoGUI-0.9.53-py3.7.e
   gg
   Copying PyAutoGUI-0.9.53-py3.7.egg to c:\program files\python37-32\lib\site-pack
   ages
   PyAutoGUI 0.9.53 is already the active version in easy-install.pth

   Installed c:\program files\python37-32\lib\site-packages\pyautogui-0.9.53-py3.7.
   egg
   Processing dependencies for PyAutoGUI==0.9.53
   Searching for pygetwindow>=0.0.5
   Reading https://pypi.org/simple/pygetwindow/
   Download error on https://pypi.org/simple/pygetwindow/: [Errno 11004] getaddrinf
   o failed -- Some packages may not be found!
   Couldn't find index page for 'pygetwindow' (maybe misspelled?)
   Scanning index of all packages (this may take a while)
   Reading https://pypi.org/simple/
   Download error on https://pypi.org/simple/: [Errno 11004] getaddrinfo failed --
   Some packages may not be found!
   No local packages or working download links found for pygetwindow>=0.0.5
   error: Could not find suitable distribution for Requirement.parse('pygetwindow>=
   0.0.5')
   ```
- pygetwindow
   I have learnt new docs commands:
   ```
   Z:\Download\PyGetWindow-0.0.9.tar\dist\PyGetWindow-0.0.9>copy PyGetWindow-0.0.9
   C:\python_package
   PyGetWindow-0.0.9\PKG-INFO
   PyGetWindow-0.0.9\README.md
   PyGetWindow-0.0.9\setup.cfg
   PyGetWindow-0.0.9\setup.py
   已复制         4 个文件。
   ```
   
   ```
   C:\python_package\PyGetWindow-0.0.9>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing src\PyGetWindow.egg-info\PKG-INFO
   writing dependency_links to src\PyGetWindow.egg-info\dependency_links.txt
   writing requirements to src\PyGetWindow.egg-info\requires.txt
   writing top-level names to src\PyGetWindow.egg-info\top_level.txt
   reading manifest file 'src\PyGetWindow.egg-info\SOURCES.txt'
   writing manifest file 'src\PyGetWindow.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build
   creating build\lib
   creating build\lib\pygetwindow
   copying src\pygetwindow\_pygetwindow_macos.py -> build\lib\pygetwindow
   copying src\pygetwindow\_pygetwindow_win.py -> build\lib\pygetwindow
   copying src\pygetwindow\__init__.py -> build\lib\pygetwindow
   creating build\bdist.win32
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pygetwindow
   copying build\lib\pygetwindow\_pygetwindow_macos.py -> build\bdist.win32\egg\pyg
   etwindow
   copying build\lib\pygetwindow\_pygetwindow_win.py -> build\bdist.win32\egg\pyget
   window
   copying build\lib\pygetwindow\__init__.py -> build\bdist.win32\egg\pygetwindow
   byte-compiling build\bdist.win32\egg\pygetwindow\_pygetwindow_macos.py to _pyget
   window_macos.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pygetwindow\_pygetwindow_win.py to _pygetwi
   ndow_win.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pygetwindow\__init__.py to __init__.cpython
   -37.pyc
   creating build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\dependency_links.txt -> build\bdist.win32\egg\E
   GG-INFO
   copying src\PyGetWindow.egg-info\requires.txt -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO

   zip_safe flag not set; analyzing archive contents...
   creating dist
   creating 'dist\PyGetWindow-0.0.9-py3.7.egg' and adding 'build\bdist.win32\egg' t
   o it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyGetWindow-0.0.9-py3.7.egg
   Copying PyGetWindow-0.0.9-py3.7.egg to c:\program files\python37-32\lib\site-pac
   kages
   Adding PyGetWindow 0.0.9 to easy-install.pth file

   Installed c:\program files\python37-32\lib\site-packages\pygetwindow-0.0.9-py3.7
   .egg
   Processing dependencies for PyGetWindow==0.0.9
   Searching for pyrect
   Reading https://pypi.org/simple/pyrect/
   Download error on https://pypi.org/simple/pyrect/: [Errno 11004] getaddrinfo fai
   led -- Some packages may not be found!
   Couldn't find index page for 'pyrect' (maybe misspelled?)
   Scanning index of all packages (this may take a while)
   Reading https://pypi.org/simple/
   Download error on https://pypi.org/simple/: [Errno 11004] getaddrinfo failed --
   Some packages may not be found!
   No local packages or working download links found for pyrect
   error: Could not find suitable distribution for Requirement.parse('pyrect')
   ```

- PyRect
   ```
   C:\python_package\PyRect-0.2.0>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing PyRect.egg-info\PKG-INFO
   writing dependency_links to PyRect.egg-info\dependency_links.txt
   writing top-level names to PyRect.egg-info\top_level.txt
   reading manifest file 'PyRect.egg-info\SOURCES.txt'
   writing manifest file 'PyRect.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build
   creating build\lib
   creating build\lib\pyrect
   copying pyrect\__init__.py -> build\lib\pyrect
   creating build\bdist.win32
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pyrect
   copying build\lib\pyrect\__init__.py -> build\bdist.win32\egg\pyrect
   byte-compiling build\bdist.win32\egg\pyrect\__init__.py to __init__.cpython-37.p
   yc
   creating build\bdist.win32\egg\EGG-INFO
   copying PyRect.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying PyRect.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyRect.egg-info\dependency_links.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyRect.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO
   zip_safe flag not set; analyzing archive contents...
   creating dist
   creating 'dist\PyRect-0.2.0-py3.7.egg' and adding 'build\bdist.win32\egg' to it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyRect-0.2.0-py3.7.egg
   Copying PyRect-0.2.0-py3.7.egg to c:\program files\python37-32\lib\site-packages

   Adding PyRect 0.2.0 to easy-install.pth file

   Installed c:\program files\python37-32\lib\site-packages\pyrect-0.2.0-py3.7.egg
   Processing dependencies for PyRect==0.2.0
   Finished processing dependencies for PyRect==0.2.0
   ```
   then
   ```
   C:\python_package\PyRect-0.2.0>cd C:\python_package\PyGetWindow-0.0.9

   C:\python_package\PyGetWindow-0.0.9>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing src\PyGetWindow.egg-info\PKG-INFO
   writing dependency_links to src\PyGetWindow.egg-info\dependency_links.txt
   writing requirements to src\PyGetWindow.egg-info\requires.txt
   writing top-level names to src\PyGetWindow.egg-info\top_level.txt
   reading manifest file 'src\PyGetWindow.egg-info\SOURCES.txt'
   writing manifest file 'src\PyGetWindow.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pygetwindow
   copying build\lib\pygetwindow\_pygetwindow_macos.py -> build\bdist.win32\egg\pyg
   etwindow
   copying build\lib\pygetwindow\_pygetwindow_win.py -> build\bdist.win32\egg\pyget
   window
   copying build\lib\pygetwindow\__init__.py -> build\bdist.win32\egg\pygetwindow
   byte-compiling build\bdist.win32\egg\pygetwindow\_pygetwindow_macos.py to _pyget
   window_macos.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pygetwindow\_pygetwindow_win.py to _pygetwi
   ndow_win.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pygetwindow\__init__.py to __init__.cpython
   -37.pyc
   creating build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\dependency_links.txt -> build\bdist.win32\egg\E
   GG-INFO
   copying src\PyGetWindow.egg-info\requires.txt -> build\bdist.win32\egg\EGG-INFO
   copying src\PyGetWindow.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO

   zip_safe flag not set; analyzing archive contents...
   creating 'dist\PyGetWindow-0.0.9-py3.7.egg' and adding 'build\bdist.win32\egg' t
   o it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyGetWindow-0.0.9-py3.7.egg
   Removing c:\program files\python37-32\lib\site-packages\PyGetWindow-0.0.9-py3.7.
   egg
   Copying PyGetWindow-0.0.9-py3.7.egg to c:\program files\python37-32\lib\site-pac
   kages
   PyGetWindow 0.0.9 is already the active version in easy-install.pth

   Installed c:\program files\python37-32\lib\site-packages\pygetwindow-0.0.9-py3.7
   .egg
   Processing dependencies for PyGetWindow==0.0.9
   Searching for PyRect==0.2.0
   Best match: PyRect 0.2.0
   Processing pyrect-0.2.0-py3.7.egg
   pyrect 0.2.0 is already the active version in easy-install.pth

   Using c:\program files\python37-32\lib\site-packages\pyrect-0.2.0-py3.7.egg
   Finished processing dependencies for PyGetWindow==0.0.9
   ```
   
   but...
   ```
   C:\python_package\PyAutoGUI-0.9.53\PyAutoGUI-0.9.53>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing PyAutoGUI.egg-info\PKG-INFO
   writing dependency_links to PyAutoGUI.egg-info\dependency_links.txt
   writing requirements to PyAutoGUI.egg-info\requires.txt
   writing top-level names to PyAutoGUI.egg-info\top_level.txt
   reading manifest file 'PyAutoGUI.egg-info\SOURCES.txt'
   reading manifest template 'MANIFEST.in'
   writing manifest file 'PyAutoGUI.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pyautogui
   copying build\lib\pyautogui\_pyautogui_java.py -> build\bdist.win32\egg\pyautogu
   i
   copying build\lib\pyautogui\_pyautogui_osx.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\_pyautogui_win.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\_pyautogui_x11.py -> build\bdist.win32\egg\pyautogui

   copying build\lib\pyautogui\__init__.py -> build\bdist.win32\egg\pyautogui
   copying build\lib\pyautogui\__main__.py -> build\bdist.win32\egg\pyautogui
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_java.py to _pyautogui_
   java.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_osx.py to _pyautogui_o
   sx.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_win.py to _pyautogui_w
   in.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\_pyautogui_x11.py to _pyautogui_x
   11.cpython-37.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\__init__.py to __init__.cpython-3
   7.pyc
   byte-compiling build\bdist.win32\egg\pyautogui\__main__.py to __main__.cpython-3
   7.pyc
   creating build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\dependency_links.txt -> build\bdist.win32\egg\EGG-INF
   O
   copying PyAutoGUI.egg-info\requires.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyAutoGUI.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO
   zip_safe flag not set; analyzing archive contents...
   creating 'dist\PyAutoGUI-0.9.53-py3.7.egg' and adding 'build\bdist.win32\egg' to
    it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyAutoGUI-0.9.53-py3.7.egg
   Removing c:\program files\python37-32\lib\site-packages\PyAutoGUI-0.9.53-py3.7.e
   gg
   Copying PyAutoGUI-0.9.53-py3.7.egg to c:\program files\python37-32\lib\site-pack
   ages
   PyAutoGUI 0.9.53 is already the active version in easy-install.pth

   Installed c:\program files\python37-32\lib\site-packages\pyautogui-0.9.53-py3.7.
   egg
   Processing dependencies for PyAutoGUI==0.9.53
   Searching for pyscreeze>=0.1.21
   Reading https://pypi.org/simple/pyscreeze/
   Download error on https://pypi.org/simple/pyscreeze/: [Errno 11004] getaddrinfo
   failed -- Some packages may not be found!
   Couldn't find index page for 'pyscreeze' (maybe misspelled?)
   Scanning index of all packages (this may take a while)
   Reading https://pypi.org/simple/
   Download error on https://pypi.org/simple/: [Errno 11004] getaddrinfo failed --
   Some packages may not be found!
   No local packages or working download links found for pyscreeze>=0.1.21
   error: Could not find suitable distribution for Requirement.parse('pyscreeze>=0.
   1.21')
   ```
   
- pyscreeze
   ```
   C:\python_package\PyAutoGUI-0.9.53\PyAutoGUI-0.9.53>cd C:\python_package\PyScree
   ze-0.1.28\PyScreeze-0.1.28

   C:\python_package\PyScreeze-0.1.28\PyScreeze-0.1.28>python setup.py install
   C:\Program Files\Python37-32\lib\distutils\dist.py:274: UserWarning: Unknown dis
   tribution option: 'requires_python'
     warnings.warn(msg)
   running install
   running bdist_egg
   running egg_info
   writing PyScreeze.egg-info\PKG-INFO
   writing dependency_links to PyScreeze.egg-info\dependency_links.txt
   writing requirements to PyScreeze.egg-info\requires.txt
   writing top-level names to PyScreeze.egg-info\top_level.txt
   reading manifest file 'PyScreeze.egg-info\SOURCES.txt'
   reading manifest template 'MANIFEST.in'
   warning: no files found matching '*.py' under directory 'pyautogui'
   writing manifest file 'PyScreeze.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   creating build
   creating build\lib
   creating build\lib\pyscreeze
   copying pyscreeze\__init__.py -> build\lib\pyscreeze
   creating build\bdist.win32
   creating build\bdist.win32\egg
   creating build\bdist.win32\egg\pyscreeze
   copying build\lib\pyscreeze\__init__.py -> build\bdist.win32\egg\pyscreeze
   byte-compiling build\bdist.win32\egg\pyscreeze\__init__.py to __init__.cpython-3
   7.pyc
   creating build\bdist.win32\egg\EGG-INFO
   copying PyScreeze.egg-info\PKG-INFO -> build\bdist.win32\egg\EGG-INFO
   copying PyScreeze.egg-info\SOURCES.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyScreeze.egg-info\dependency_links.txt -> build\bdist.win32\egg\EGG-INF
   O
   copying PyScreeze.egg-info\requires.txt -> build\bdist.win32\egg\EGG-INFO
   copying PyScreeze.egg-info\top_level.txt -> build\bdist.win32\egg\EGG-INFO
   zip_safe flag not set; analyzing archive contents...
   creating dist
   creating 'dist\PyScreeze-0.1.28-py3.7.egg' and adding 'build\bdist.win32\egg' to
    it
   removing 'build\bdist.win32\egg' (and everything under it)
   Processing PyScreeze-0.1.28-py3.7.egg
   Copying PyScreeze-0.1.28-py3.7.egg to c:\program files\python37-32\lib\site-pack
   ages
   Adding PyScreeze 0.1.28 to easy-install.pth file

   Installed c:\program files\python37-32\lib\site-packages\pyscreeze-0.1.28-py3.7.
   egg
   Processing dependencies for PyScreeze==0.1.28
   Searching for Pillow>=5.2.0
   Reading https://pypi.org/simple/Pillow/
   Download error on https://pypi.org/simple/Pillow/: [Errno 11004] getaddrinfo fai
   led -- Some packages may not be found!
   Couldn't find index page for 'Pillow' (maybe misspelled?)
   Scanning index of all packages (this may take a while)
   Reading https://pypi.org/simple/
   Download error on https://pypi.org/simple/: [Errno 11004] getaddrinfo failed --
   Some packages may not be found!
   No local packages or working download links found for Pillow>=5.2.0
   error: Could not find suitable distribution for Requirement.parse('Pillow>=5.2.0
   ')
   ```
   
- Pillow
   ```
   C:\python_package\Pillow-7.0.0>python setup.py install
   running install
   running bdist_egg
   running egg_info
   writing src\Pillow.egg-info\PKG-INFO
   writing dependency_links to src\Pillow.egg-info\dependency_links.txt
   writing top-level names to src\Pillow.egg-info\top_level.txt
   reading manifest file 'src\Pillow.egg-info\SOURCES.txt'
   reading manifest template 'MANIFEST.in'
   warning: no files found matching '*.c'
   warning: no files found matching '*.h'
   warning: no files found matching '*.sh'
   warning: no previously-included files found matching '.appveyor.yml'
   warning: no previously-included files found matching '.coveragerc'
   warning: no previously-included files found matching '.codecov.yml'
   warning: no previously-included files found matching '.editorconfig'
   warning: no previously-included files found matching '.readthedocs.yml'
   warning: no previously-included files found matching 'azure-pipelines.yml'
   warning: no previously-included files matching '.git*' found anywhere in distrib
   ution
   warning: no previously-included files matching '*.pyc' found anywhere in distrib
   ution
   warning: no previously-included files matching '*.so' found anywhere in distribu
   tion
   no previously-included directories found matching '.azure-pipelines'
   no previously-included directories found matching '.travis'
   writing manifest file 'src\Pillow.egg-info\SOURCES.txt'
   installing library code to build\bdist.win32\egg
   running install_lib
   running build_py
   running build_ext


   The headers or library files could not be found for zlib,
   a required dependency when compiling Pillow from source.

   Please see the install instructions at:
      https://pillow.readthedocs.io/en/latest/installation.html

   Traceback (most recent call last):
     File "setup.py", line 892, in <module>
       zip_safe=not (debug_build() or PLATFORM_MINGW),
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\__init__.py",
   line 145, in setup
       return distutils.core.setup(**attrs)
     File "C:\Program Files\Python37-32\lib\distutils\core.py", line 148, in setup
       dist.run_commands()
     File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 966, in run_co
   mmands
       self.run_command(cmd)
     File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
   mmand
       cmd_obj.run()
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
   l.py", line 67, in run
       self.do_egg_install()
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
   l.py", line 109, in do_egg_install
       self.run_command('bdist_egg')
     File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
   mand
       self.distribution.run_command(command)
     File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
   mmand
       cmd_obj.run()
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\bdist_
   egg.py", line 172, in run
       cmd = self.call_command('install_lib', warn_dir=0)
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\bdist_
   egg.py", line 158, in call_command
       self.run_command(cmdname)
     File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
   mand
       self.distribution.run_command(command)
     File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
   mmand
       cmd_obj.run()
     File "C:\Program Files\Python37-32\lib\site-packages\setuptools\command\instal
   l_lib.py", line 11, in run
       self.build()
     File "C:\Program Files\Python37-32\lib\distutils\command\install_lib.py", line
    107, in build
       self.run_command('build_ext')
     File "C:\Program Files\Python37-32\lib\distutils\cmd.py", line 313, in run_com
   mand
       self.distribution.run_command(command)
     File "C:\Program Files\Python37-32\lib\distutils\dist.py", line 985, in run_co
   mmand
       cmd_obj.run()
     File "C:\Program Files\Python37-32\lib\distutils\command\build_ext.py", line 3
   40, in run
       self.build_extensions()
     File "setup.py", line 687, in build_extensions
       raise RequiredDependencyException(f)
   __main__.RequiredDependencyException: zlib

   During handling of the above exception, another exception occurred:

   Traceback (most recent call last):
     File "setup.py", line 907, in <module>
       raise RequiredDependencyException(msg)
   __main__.RequiredDependencyException:

   The headers or library files could not be found for zlib,
   a required dependency when compiling Pillow from source.

   Please see the install instructions at:
      https://pillow.readthedocs.io/en/latest/installation.html
   ```
   
- It seems that we return the position where we come across. So I begin to read the code of Pillow by vscode.
   
   
   
   
   
   













