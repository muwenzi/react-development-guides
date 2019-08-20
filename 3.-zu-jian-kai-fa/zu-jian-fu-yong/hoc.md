---
description: >-
  高阶组件（HOC）是react中对组件逻辑进行重用的高级技术。但高阶组件本身并不是React
  API。它只是一种模式，这种模式是由react自身的组合性质必然产生的。
---

# HOC

[高阶组件](https://www.reactjscn.com/docs/higher-order-components.html)类似于函数式编程中的高阶函数，就是一个函数式组件接受一个组件作为参数，经过一系列加工后，最后返回一个新的组件。看下面的代码示例，withUser函数就是一个高阶组件，它返回了一个新的组件，这个组件具有了它提供的获取用户信息的功能。

```jsx
const withUser = WrappedComponent => {
  const user = sessionStorage.getItem("user");
  return props => <WrappedComponent user={user} {...props} />;
};

const UserPage = props => (
  <div class="user-container">
    <p>My name is {props.user}!</p>
  </div>
);

export default withUser(UserPage);
```

对比组件将props属性转变成UI，高阶组件则是将一个组件转换成另一个新组件。高阶组件是通过将原组件 包裹（wrapping） 在容器组件（container component）里面的方式来 组合（composes） 使用原组件。高阶组件就是一个没有副作用的纯函数。高阶组件并不关心数据是如何以及为什么被使用。

{% hint style="danger" %}
**强制**：不要在高阶组件内部修改（或以其它方式修改）原组件的原型属性。
{% endhint %}





