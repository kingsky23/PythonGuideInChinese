.. _install-windows:

在Windows上安装Python
============================

首先，从Python官方网站下载 `最新版 <http://python.org/ftp/python/2.7.6/python-2.7.6.msi>`_
的Python 2.7。如果你想确保安装的是最新版本的Python，在 `Python官方网站 <http://python.org>`_
上使用"Windows Installer"链接

Windows版的Python是作为MSI安装包提供的，只要双击即可安装。MSI安装包允许管理员自动
安装这些工具

按照设计，Python被安装到带有版本号的路径下，例如：Python 2.7会被安装在
``C:\Python27\`` ，所以你可以在一个系统中安装多个版本的Python而不冲突。
当然，只有一个解析器可以被作为打开Python类型文件的默认程序。此外，
Python并不会自动设置 ``PATH`` 环境变量，所以你可以借此来控制使用哪一个版本的Python

每一次都要输入Python解析器的完整路径确实很操蛋，所以将你要默认使用得Python版本得路径
加入 ``PATH`` 环境变量。假设你的Python安装在 ``C:\Python27\`` ，将这个路径加入你的PATH::

    C:\Python27\;C:\Python27\Scripts\

You can do this easily by running the following in ``powershell``::
你也可以直接运行下述命令通过 ``powershell`` ::

    [Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Python27\;C:\Python27\Scripts\", "User")

第二个(``Scripts``)目录将接受一些命令文件，如果安装了一些包，所以这是个十分有用的附加项。
其实你不需要安装或配置其它的东西便可以使用Python了。但是在你开始使用Python前，我还是强烈
推荐你安装下面一节描述的工具和库。特别的，你最好一直安着Setuptools，它让安装第三方库变得
很easy

Setuptools + Pip
----------------

所有第三方Python软件中最为重要的当属Setuptools，它可以扩展标准库提供的包和工具。一旦你装
了Setuptools，你只需一条简单的命令便可下载和安装任何复杂的Python。它还允许你让你的Python
软件也具有这种网络安装的能力

要安装最新版的Setuptools, 运行这个Python脚本: 
`ez_setup.py <https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py>`_

现在你有一个新的命令可以用了: **easy_install**. 但这个命令的名声不太好，很多人不推荐它，
所以我们使用另一个安装工具: **pip**. 不像easy_install，pip允许你安装、卸载、更新你安装的
第三方工具和库

要安装最新版pip，运行下面这个Python脚本:
`get-pip.py <https://raw.github.com/pypa/pip/master/contrib/get-pip.py>`_


Virtualenv
----------

安装完Setuptools和Pip后，下一个要安装的开发工具便是
`virtualenv <http://pypi.python.org/pypi/virtualenv/>`_. 使用pip安装

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
