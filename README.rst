

Theano 在深度学习框架中是祖师级的存在。
它的开发始于 2007，早期开发者包括传奇人物 Yoshua Bengio 和 Ian Goodfellow。

Theano 基于 Python，是一个擅长处理多维数组的库（这方面它类似于 NumPy）。
当与其他深度学习库结合起来，它十分适合数据探索。它为执行深度学习中大规模神经网络算法的运算所设计。
其实，
它可以被更好地理解为一个数学表达式的编译器：
用符号式语言定义你想要的结果，该框架会对你的程序进行编译，来高效运行于 GPU 或 CPU。

Theano 像是一个研究平台多过是一个深度学习库。

你需要从底层开始做许多工作，来创建你需要的模型。

比方说，Theano 没有神经网络的分级。

但随着这些年的发展，大量基于 Theano 的开源深度学习库被开发出来，

包括 Keras, Lasagne 和 Blocks。

[Pylearn2 是建立在Theano之上的一个机器学习库](https://github.com/Ewenwan/pylearn2)
  
很少开发者会使用“裸奔”的 Theano，多数人需要辅助的 API。
顺便说一句，Theano 是一整套生态系统，别只用它裸奔，然后抱怨不好用。

在过去的很长一段时间内，Theano 是深度学习开发与研究的行业标准。
而且，由于出身学界，它最初是为学术研究而设计，这导致深度学习领域的许多学者至今仍在使用 Theano。
但随着 Tensorflow 在谷歌的支持下强势崛起，Theano 日渐式微，使用的人越来越少。
这过程中的标志性事件是：创始者之一的 Ian Goodfellow 放弃 Theano 转去谷歌开发 Tensorflow。

因此，资深一些的开发者往往认为，对于深度学习新手，用Theano 练练手并没有任何坏处。
但对于职业开发者，还是建议用 Tensorflow。

优点：
Python + NumPy 的组合

使用计算图

RNN 与计算图兼容良好

有 Keras 和 Lasagne 这样高层的库

不少开发者反映，它的学习门槛比Tensorflow 低

缺点：
本身很底层

比 Torch 臃肿

不支持分布式

有的错误信息没什么用

大模型的编译时间有时要很久

对事先训练过的模型支持不足

用的人越来越少


============================================================================================================
`MILA will stop developing Theano <https://groups.google.com/d/msg/theano-users/7Poq8BZutbY/rNCIfvAEAwAJ>`_.
============================================================================================================


To install the package, see this page:
   http://deeplearning.net/software/theano/install.html

For the documentation, see the project website:
   http://deeplearning.net/software/theano/

Related Projects:
   https://github.com/Theano/Theano/wiki/Related-projects

It is recommended that you look at the documentation on the website, as it will be more current than the documentation included with the package.

In order to build the documentation yourself, you will need sphinx. Issue the following command:

::

   python ./doc/scripts/docgen.py

Documentation is built into ``html/``

The PDF of the documentation can be found at ``html/theano.pdf``

================
DIRECTORY LAYOUT
================

``Theano`` (current directory) is the distribution directory.

* ``Theano/theano`` contains the package
* ``Theano/theano`` has several submodules:
 
  * ``gof`` + ``compile`` are the core
  * ``scalar`` depends upon core
  * ``tensor`` depends upon ``scalar``
  * ``sparse`` depends upon ``tensor``
  * ``sandbox`` can depend on everything else

* ``Theano/examples`` are copies of the example found on the wiki
* ``Theano/benchmark`` and ``Theano/examples`` are in the distribution, but not in
  the Python package
* ``Theano/bin`` contains executable scripts that are copied to the bin folder
  when the Python package is installed
* Tests are distributed and are part of the package, i.e. fall in
  the appropriate submodules
* ``Theano/doc`` contains files and scripts used to generate the documentation
* ``Theano/html`` is where the documentation will be generated
