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


















