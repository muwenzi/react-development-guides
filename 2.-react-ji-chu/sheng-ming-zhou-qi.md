# 生命周期

## React &lt; v16.3

![&#x56FE;&#xFF1A;React &amp;lt; v16.3 &#x751F;&#x547D;&#x5468;&#x671F;&#x56FE;](../.gitbook/assets/image%20%281%29.png)



* 红色是在 v17 版本后废弃的生命周期。
* 细字体的声明周期是不常用的，加粗是常用的。

## React &gt; v16.3

React v16.3，引入了两个新的生命周期函数：

* **getDerivedStateFromProps**
* **getSnapshotBeforeUpdate**

{% hint style="info" %}
**Tips**：`getDerivedStateFromProps` 实际上就是用来取代以前的 `componentWillMount` 和 `componentWillReceiveProps`
{% endhint %}

随着 `getDerivedStateFromProps` 的推出，同时deprecate了一组生命周期API，包括：

* **componentWillReceiveProps**
* **componentWillMount**
* **componentWillUpdate**

新的生命周期图如下图所示：

![&#x56FE;&#xFF1A;React &amp;gt; v16.3 &#x751F;&#x547D;&#x5468;&#x671F;&#x56FE;](../.gitbook/assets/image%20%282%29.png)

* 细字体的声明周期是不常用的，加粗是常用的。

