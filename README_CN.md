# MteRT-Standard
Malt编程语言目标环境运行时标准（LyzhStandard 2019-5）

MteRT是Malt目标环境运行时（即Malt target environment Runtime）的简称。

## 命名规则

一切MteRT可运行包命名方式皆为Malt后接**平台**和**实现语言**或其缩写，例如**MteRT-wb-ts**即意为**在网络浏览器(Web Browser)平台上运行的，使用TypeScript编写的MteRT**。

## 实现标准

一些MteRT皆需要正确实现MteRT ByteCode Images和MteRT Global Dump Images的加载和运行(在[images.md](/images.md)和[dump.md](/dump.md)处查看)。

一切MteRT皆需要提供能在安全点（Safe Point）时将整机（虚拟机）快照Dump到任意储存介质（通常是磁盘）和Load进运行时环境中的功能，同时该Images文件能在所有部署了该MteRT的机器、平台和环境中运行（也就是俗称的一次编译多处执行），但提供的任意外部调用需要提供在环境中部署。

一切MteRT需要提供一种方式以增加特性。

我根据基本要求和平台性质制定了多个标准，使用者可以在这些标准上任意**增加**特性。

### MteRT的标准环境

#### Pure 环境
Pure环境一般用于编译后预运行，该标准不可消减特性（既为最小标准环境）。

一般来说负责类的组装等，包含MteRT的一切基本类，具体请参照[BaseClass](/BaseClass)。

#### Core 环境

Core环境在Pure环境的基础上，增加了标准输入输出，多线程等内容

#### OS 环境
OS环境可以实现任意标准的特性，具体应具体OS环境的不同而不同。OS环境应内建一个操作系统，用于在包括单片机在内的裸机环境中运行。
