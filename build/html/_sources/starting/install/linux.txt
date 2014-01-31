.. _install-linux:

在Linux上安装Python
==========================

最新版本的Ubuntu和Fedora **自带Python 2.7** 

最新版的Redhat Enterprise (RHEL) 和 CentOS自带Python 2.6。
一些老版本的RHEL和CentOS自带Python 2.4，不过这个版本对现代开发来讲太老了。
幸运的是， `Extra Packages for Enterprise Linux`_ 包括了基于Fedora的高质量的附加包。
这个仓库包括了一个专门设计与系统自带兼容的Python 2.4兼容的Python 2.6的包

.. _Extra Packages for Enterprise Linux: http://fedoraproject.org/wiki/EPEL

你不需要安装或设置任何其他东西。在你开始用Python写程序之前，
我强烈推荐你安装下一节中叙述的工具和库。此外，你应该安装Distribute，
因为它可以让安装第三方库变的很简单

Distribute & Pip
----------------

在所有第三方Python软件中最至关重要的便是Distribute，它可以扩展由distutils
提供的打包和安装工具。一旦你安装了Distribute，你可以仅通过一条命令来下载、
安装任何符合要求的Python软件。同时它还允许你很方便的给自己的模块也加上这种强大的
网络安装能力。

为了给Linux安装最新版的Distribute，请运行下面这个Python脚本 
`python-distribute <http://python-distribute.org/distribute_setup.py>`_

最新的``easy_install``命令受到了许多反对，所以我们讲安装它的替代品: **pip**
Pip允许卸载包，而且可以积极维护它们，不像easy_install

安装pip，只需要简单的打开一个命令窗口然后运行

.. code-block:: console

    $ easy_install pip


Virtualenv
----------

安装好Distribute和Pip后，下一个你应该安装的开发工具是
`virtualenv <http://pypi.python.org/pypi/virtualenv/>`_

.. code-block:: console

    $ pip install virtualenv

virtualenv提供了创建虚拟Python环境的能力，他们彼此之间、以及和主要的Python安装之间，
不互相影响。如果你在开始编码之前安装了virtualenv，你可以用它为每一个项目创建完全干净的
Python环境。这对于不同框架之间互相影响的Web开发来讲尤其重要

为了建立一个新的Python环境，将工作目录改变为你想要存储新环境的地方，
然后在你的项目目录中运行virtualenv

.. code-block:: console

    $ virtualenv --distribute venv

使用环境时，执行``source venv/bin/activate``。你的命令窗口将显示当前活动的
环境。一旦你在当前虚拟环境中完成工作，执行``deactivate``来还原设置

每一个新的环境都会自动的包括``pip``的一份拷贝，所以你可以随意安装你想使用的第三方
库和工具。将你的代码放在环境中的子目录下。当你不再需要特殊环境时，只需简单的将你的代码
复制出来，然后删除环境的主目录即可


--------------------------------

本页是一个和 `另一个指南 <http://www.stuartellis.eu/articles/python-development-windows/>`_ 的混合版本，但都基于同样的协议。

