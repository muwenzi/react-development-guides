# 组件提纯

非纯代码虽然有害但不可或缺。大多数应用都需要全局状态、网络请求、本地存储等等。你能做的只是将非纯代码从纯代码中隔离出来，这一过程又成为 **提纯（purification）**。

![&#x7EC4;&#x4EF6;&#x63D0;&#x7EAF;&#x7C7B;&#x6BD4;&#x56FE;](../../.gitbook/assets/pure.jpeg)

孤立的非纯代码有明确的副作用，或对全局状态的依赖。在隔离状态下，非纯代码对系统中其余部分的不可预测性影响会降低很多。
