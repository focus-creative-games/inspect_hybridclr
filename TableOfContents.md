# Inspect il2cpp&huatuo

我们在实现huatuo过程中，深入研究了CLI规范与il2cpp实现，积累了大量宝贵的经验。考虑到国内游戏行业对clr及il2cpp相关的资料不多，我们希望将这些知识系统性地整理出来，帮助那些渴望深入研究Unity下CLR Runtime实现的开发者们，更好了掌握相关知识。

## Inspect il2cpp 目录

- il2cpp 序章
  - il2cpp 介绍
  - il2cpp il2cpp 架构及源码结构介绍
  - il2cpp 安装、编译及调试
- il2cpp 运行时实现
  - il2cpp Runtime 初始化流程剖析
  - il2cpp metadata （此节内容极其庞大）
    - CLI metadata 简略介绍
    - il2cpp metadata 初始化流程剖析
    - persistent metadata 即 global-metadata.data 介绍
    - runtime metadata 介绍
  - il2cpp IL to c++ 代码的转换
    - 基础指令集
    - 对象模型相关指令 （内容极其庞大）
    - 异常机制
    - 泛型共享机制
    - PInvoke 与 MonoPInvokeCallbackAttribute相关。(一个有趣的问题：il2cpp中lua回调c#函数相比与回调普通c函数，多了哪些开销？)
    - icalls
    - delegate
    - 反射相关支持
    - 跨平台相关
  - 类型初始化 Class::Init 流程剖析
  - 泛型类实现
  - 泛型函数实现
  - 泛型共享机制
  - 异常机制
  - 反射相关实现
  - 值类型相关机制
  - box与unbox相关机制
  - object、string、Array、TypedReference等一些基础BCL类型的探究
  - icalls 实现
  - il2cpp及mono的bug介绍
  - il2cpp gc管理
  - il2cpp 多线程及内存模型处理
- 2018-2022中il2cpp实现的演化

## Inspect huatuo 目录

- huatuo 序章
  - huatuo基础知识及原理介绍
  - huatuo的框架结构
- metadata
  - metadata 加载
  - metadata动态注册
    - 类型注册
    - generic class and method处理
    - 桥接函数签名
- interpreter
  - 寄存器指令集设计
  - transform实现
    - 基础实现
    - 指令集优化
  - virtual Execution System
    - Thread Interpreter Stack
    - Interpreter Frame实现与优化
    - localloc 与 Local Memory Pool
    - 桥接函数
    - 指令实现
    - instinct函数
    - reflection相关实现
    - extern函数实现
  - 跨平台兼容性处理
    - 内存对齐
    - x86与arm系列的abi差别
    - 32位与64位
  - AOT泛型 （基于补充元数据的泛型实例化技术）
  - AOT hotfix实现
- misc
  - 解决Unity资源上挂载interpreter脚本
  - gc 处理
  - 多线程相关处理
- test框架
  - 测试用例项目
    - bootstrap cpp测试集
    - .net c#测试集
    - 生成测试报告
  - 测试工具
    - 创建多版本多平台的测试项目
    - 运行测试用例，收集测试报告
    - 生成最终测试报告
  - 自动化测试DevOps框架
