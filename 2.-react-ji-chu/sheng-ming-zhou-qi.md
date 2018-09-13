# 生命周期

## Before React v16.3

![React v15 &#x751F;&#x547D;&#x5468;&#x671F;&#x56FE;](../.gitbook/assets/88e11709488aeea3f9c6595ee4083bf3.bin)

## After React v16.3

React v16.3，引入了两个新的生命周期函数：

* **getDerivedStateFromProps**
* **getSnapshotBeforeUpdate**

{% hint style="info" %}
**Tips**：getDerivedStateFromProps 实际上就是用来取代以前的 componentWillReceiveProps
{% endhint %}

随着 `getDerivedStateFromProps` 的推出，同时deprecate了一组生命周期API，包括：

* **componentWillReceiveProps**
* **componentWillMount**
* **componentWillUpdate**

新的生命周期图如下图所示：

![React v16.3 &#x751F;&#x547D;&#x5468;&#x671F;&#x56FE;](../.gitbook/assets/ping-mu-kuai-zhao-20180619-xia-wu-5.32.22.png)

