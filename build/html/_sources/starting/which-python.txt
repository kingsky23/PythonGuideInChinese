选择一个解析器
======================

.. _which-python:

当前 (Python 2)
~~~~~~~~~~~~~~~~

如果你还在纠结选择哪个Python解析器，我 *强烈* 推荐使用Python 2.7.x，除非你有其他
不用的理由

如果你打算使用新的Python模块也应用Python 2.7.x。如果你打算让它在2.7上工作，你也
可以添加其他对老版本的支持

未来 (Python 3)
~~~~~~~~~~~~~~~~~~~~~

    Python 2.x是现状，Python 3.x则是全新的东西

`更多内容 <http://wiki.python.org/moin/Python2orPython3>`_

另一方面，Python 3和Python 2有极大的不同，所以写出同时兼容Python 2和Python 3
的代码是十分困难的过程

不过还是可以 `写出同时兼容Python 2.6, 2.7和3.3的代码
<http://lucumr.pocoo.org/2013/5/21/porting-to-python-3-redux/>`_ 。根据你所写软件的不同，这可能会极度困难，如果你只是个初学者的话，
这里还有许多更重要的事需要你操心

实现
~~~~~~~~~~~~~~~

这里有许多主流基于不同后端的Python实现

CPython
-------

`CPython <http://www.python.org>`_ 是Python的一个参考实现，用C语言编写。它将Python
代码编译成中间字节码后被虚拟机所解析。人们时常提起的*Python*不仅是指语言本身常常
还指这个实现。它提供对Python包和C语言扩展模块最高级别的兼容性

如果你编写开源开源Python代码并希望有更多的使用者，以CPython为目标是最好的选择。
如果你需要使用那些依赖C语言扩展的包（比如numpy），CPython将是你唯一的选择

作为参考版实现，CPythonz支持所有Python语言的版本。Python 3只有CPython的实现

PyPy
----


`PyPy <http://pypy.org/>`_ 由一个叫做RPython的“限制静态类型？”的Python语言子集实
现。这个解释器具有实时编译器并支持多种后端(C, CLI, JVM)

PyPy旨在保证对CPython最大兼容性的情况下尽可能提高性能

如果你想要尽可能提高你的Python代码的性能的话，PyPy值得一试。在一系列基准测试中，
它`比CPython快5倍<http://speed.pypy.org/>`_

当前PyPy支持Python 2.7. [#pypy_ver]_

Jython
------

`Jython <http://www.jython.org/>`_ 是一个将Python代码编译为Java字节码并在JVM中执行的
Python实现。它的额外优势在于可以像调用Python模块一样调用Java的类

如果你需要针对JVM写Python代码，Jython是最好的选择

Jython当前支持到Python 2.5. [#jython_ver]_

IronPython
----------

`IronPython <http://ironpython.net/>`_ 是一个基于.NET框架的Python实现。它既可以使用
Python库还可以使用.NET框架的库，同时还可以与其他.NET语言交互


`Python Tools for Visual Studio <http://ironpython.net/tools/>`_ 直接将IronPython
集成进Visual Studio开发环境，对Windows开发者来讲这将是个好选择

IronPython当前支持到Python 2.7. [#iron_ver]_ 


.. [#pypy_ver] http://pypy.org/compat.html

.. [#jython_ver] http://wiki.python.org/jython/JythonFaq/GeneralInfo#Is_Jython_the_same_language_as_Python.3F

.. [#iron_ver] http://ironpython.codeplex.com/releases/view/81726
