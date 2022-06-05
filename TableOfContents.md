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
      - Il2CppType、Il2CppTypeDefinition和Il2CppClass
      - Method 和 Property
      - Field
      - Const变量
      - Token
      - Custom Attribute
      - 其他
  - il2cpp gc管理
  - il2cpp 多线程及内存模型处理
  - il2cpp IL to c++ 代码的转换
    - 基础指令集
    - 对象模型相关指令 （内容极其庞大）
    - 异常机制
    - 泛型共享机制
    - PInvoke 与 MonoPInvokeCallbackAttribute相关。 (一个有趣的问题：il2cpp中lua回调c#函数相比与回调普通c函数，多了哪些开销？)
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

## Inspect huatuo 目录

TODO
