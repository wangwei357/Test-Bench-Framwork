# Test Bench Framework框架简介

- ## Test Becnh Framework 框架概览

  Test Becnh Framework 是测试序列管理软件框架，框架基于LabVIEW2019开发，并且以第三方工具包形式发布，主要用于测控行业快速开发调试测试序列以及上位机软件界面。

  框架的主要特点是可以并发执行多个不同的测试序列（多工站），也可以并行执行多个相同的测试序列（多槽位），以及通过框架API来控制Test Engine，用户可以通过调用API来开发定制不同的用户界面。

  框架还集成了MSA分析功能，用户只需要调用相关的API就可以用产品测试的历史数据导出MSA分析报表。

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd1NRUtP2pyTWibVicujdicRFYmmTDqlb1JZbHdeP1BvaicFibPyZXia8ibf9HreDYVlB9LwCbicuJd46nRSBg/640?wx_fmt=png)

- ## Test Becnh Framework 框架主要功能

   框架包含两个核心组成部分：测试引擎，测试序列编辑软件

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbgaD3BjczdtPD5liaiawvJQzJP0nVVJo2hzUoW0Wuxyt9V3Zkay32LHtg/640?wx_fmt=png)

- ## Test Becnh Framework 框架使用流程

  简单四个步骤帮助你快速开发FCT&EOL上位机软件

  ### 一，安装Test Becnh Framework 框架

     通过VIPM软件安装框架，由于框架范例使用了第三方工具包所以安装的过程中需要联网，在安装之前需要关闭杀毒软件的实时扫描功能，框架只支持LabVIEW2019 32位以及以上版本。

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5Wfmtb5JEquERLicZMCqs0qx6cUcCjWCdnkr3PiaUNym75JC9GeqrVdeQsFUFw/640?wx_fmt=png)

###   二，使用框架提供的API编写用户UI

​     框架的API的功能是控制Test Engine以及获取Test Engine的反馈。详细的使用方法，在框架的开发文档中会有详细说明(大家关注本公众号后面也会有文章以及视频详细讲解框架API的用法)，用户也可以通过运行范例来了解框架API的用法。

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbY0fgkLZwJ1HcCCAgvTSjicxC8aHpsr4lYGqAUJsFAQ0yYjVyvReHZOw/640?wx_fmt=png)

​    框架提供了两个UI范例：简单范例和复杂范例

​    简单UI范例仅包含了基本功能，包括执行测试序列和查询历史数据。程序框图结构比较简单便于用户理解框架API的功能和执行过程。

​    简单范例包含单工站单槽位的范例和多工站单槽位的范例

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbA5PSqt1jvx2iahLvqJGhq3K5r6cYPTHF1h58mMzhzIu7EaibbYFVichlw/640?wx_fmt=png)

![img](https://mmbiz.qpic.cn/sz_mmbiz_gif/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbYuEeXJWtxy5HicSMTB4QZib92pCNdhibfrpBQ3DxsFmTNELaIeXcJ4Ldw/640?wx_fmt=gif)

  复杂UI范例包含了一些附加的功能模块和子界面例如用户管理界面，数据查询界面，系统设置界面等等，还增加了硬件抽象层设计，方便上位机与PLC以及扫码枪等外围设备进行交互。

  复杂UI范例是基于单工站多槽位的模式设计的,可以通过设置来生成多个产品测试界面。

![img](https://mmbiz.qpic.cn/sz_mmbiz_gif/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbllFreyUj7q7tAy2ia7lckX0mF05P6KJ6wQ3YTHCY2JY9wjMiaIwWmeDw/640?wx_fmt=gif)

  界面范例是完全开源的，用户可以依据项目的实际情况进行修改或者重新定制。

###   三，使用框架的VI脚本工具自动生成符合框架规范的TestVI

​     用户开发好测试用例之后，在工程文件中选中需要生成TestVI的VI然后右键选择Test Bench Framework->Create Test VI，VI脚本工具会自动生成一个TestVI文件并且添加到库文件，也可以使用框架API中的Assert选版中的函数手动生成TestVI文件。

  编辑好TestVI文件后，需要将TestVI库打包生成一个PPL文件供SequenceEdit文件使用。

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5Wfmtbvnian5MJ6N2icyAb2qS8E7Dicmoia8SiaBmiavDGqlg90ufabxDdKUvwib9uQ/640?wx_fmt=png)

###   四，使用SequenceEdit软件编辑和调试测试序列

​     生成TestVI库文件之后，在项目界面工具栏点击SequenceEdit（绿色小勾图标）按钮启动SequenceEdit软件。

​     打开软件之后就可以编辑和调试Sequence文件了，软件的详细用法在软件帮助文档中有详细说明(大家关注本公众号后面也会有文章以及视频详细讲解测试序列编辑软件的用法)。

​     编辑调试完成之后生成的Sequence文件就可以直接用第一步开发的用户UI调用了。

![img](https://mmbiz.qpic.cn/sz_mmbiz_gif/tfs9a3ibTpd0v0lbt9J1Ras1l0ia5WfmtbnL1yMjflDUibeNKCH9qiaytPNhoGzUuCdfrpiaqINhoNSyvBh0MG1mvmA/640?wx_fmt=gif)

- ## Test Becnh Framework框架开发历程

    Test Becnh Framework框架主体开发历时三年，有20多位测控工程师参与框架测试，目前已经应用在多个汽车电子零部件产品的自动化产线的测试设备中。

    在今后的时间中Test Becnh Framework框架会不断的增加一些新的功能，来帮助工程师更快的开发和调试EOL&FCT设备，让测控工程师们能够有更多的时间和精力来解决产品测试相关的问题。
