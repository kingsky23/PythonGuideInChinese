.. _install-windows:

在Windows上安装Python
============================

首先，从Python官方网站下载 `最新版 <http://python.org/ftp/python/2.7.6/python-2.7.6.msi>`_
的Python 2.7。如果你想确保安装的是最新版本的Python，在 `Python官方网站 <http://python.org>`_
上使用"Windows Installer"链接

Windows版的Python是作为MSI安装包提供的，只要双击即可安装。MSI安装包允许管理员自动
安装这些工具

按照设计，Python被安装到带有版本号的路径下，例如：Python 2.7会被安装在
``C:\Python27\``，所以你可以在一个系统中安装多个版本的Python而不冲突。
当然，只有一个解析器可以被作为打开Python类型文件的默认程序。此外，
Python并不会自动设置``PATH``环境变量，所以你可以借此来控制使用哪一个版本的Python

Typing the full path name for a Python interpreter each time quickly gets
tedious, so add the directories for your default Python version to the PATH.
Assuming that your Python installation is in ``C:\Python27\``, add this to your
PATH::

    C:\Python27\;C:\Python27\Scripts\

You can do this easily by running the following in ``powershell``::

    [Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Python27\;C:\Python27\Scripts\", "User")

The second (``Scripts``) directory receives command files when certain
packages are installed, so it is a very useful addition.
You do not need to install or configure anything else to use Python. Having
said that, I would strongly recommend that you install the tools and libraries
described in the next section before you start building Python applications for
real-world use. In particular, you should always install Setuptools, as it
makes it much easier for you to use other third-party Python libraries.

Setuptools + Pip
----------------

The most crucial third-party Python software of all is Setuptools, which
extends the packaging and installation facilities provided by the distutils in
the standard library. Once you add Setuptools to your Python system you can
download and install any compliant Python software product with a single
command. It also enables you to add this network installation capability to
your own Python software with very little work.

To obtain the latest version of Setuptools for Windows, run the python script
available here: `ez_setup.py <https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py>`_


You'll now have a new command available to you: **easy_install**. It is
considered by many to be deprecated, so we will install its replacement:
**pip**. Pip allows for uninstallation of packages, and is actively maintained,
unlike easy_install.

To install pip, run the python script available here:
`get-pip.py <https://raw.github.com/pypa/pip/master/contrib/get-pip.py>`_


Virtualenv
----------

After Distribute & Pip, the next development tool that you should install is
`virtualenv <http://pypi.python.org/pypi/virtualenv/>`_. Use pip

.. code-block:: console

    > pip install virtualenv

The virtualenv kit provides the ability to create virtual Python environments
that do not interfere with either each other, or the main Python installation.
If you install virtualenv before you begin coding then you can get into the
habit of using it to create completely clean Python environments for each
project. This is particularly important for Web development, where each
framework and application will have many dependencies.


To set up a new Python environment, change the working directory to where ever
you want to store the environment, and run the virtualenv utility in your
project's directory

.. code-block:: console

    > virtualenv venv

To use an environment, run the ``activate.bat`` batch file in the ``Scripts``
subdirectory of that environment. Your command prompt will change to show the
active environment. Once you have finished working in the current virtual
environment, run the ``deactivate.bat`` batch file to restore your settings to
normal.

Each new environment automatically includes a copy of ``pip`` in the
``Scripts`` subdirectory, so that you can setup the third-party libraries and
tools that you want to use in that environment. Put your own code within a
subdirectory of the environment, however you wish. When you no longer need a
particular environment, simply copy your code out of it, and then delete the
main directory for the environment.



--------------------------------

This page is a remixed version of `another guide <http://www.stuartellis.eu/articles/python-development-windows/>`_,
which is available under the same license.
