# Hooks

## 什么是State Hooks？

看一个例子，我们分解来看到底state hooks做了什么：

```jsx
import { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### 声明一个状态变量

```jsx
import { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);
```

`useState`是react自带的一个hook函数，它的作用就是用来声明状态变量。`useState`这个函数接收的参数是我们的状态初始值（initial state），它返回了一个数组，这个数组的第`[0]`项是当前当前的**状态值**，第`[1]`项是可以改变状态值的**方法函数**。

所以我们做的事情其实就是，声明了一个状态变量count，把它的初始值设为0，同时提供了一个可以更改count的函数setCount。

### 读取状态值

```jsx
<p>You clicked {count} times</p>
```

很简单，因为我们的状态count就是一个单纯的变量而已，我们再也不需要写成`{this.state.count}`这样了。

### 更新状态

```jsx
<button onClick={() => setCount(count + 1)}>
  Click me
</button>
```

当用户点击按钮时，我们调用setCount函数，这个函数接收的参数是修改过的新状态值。接下来的事情就交给react了，react将会重新渲染我们的Example组件，并且使用的是更新后的新的状态，即`count=1`。这里我们要停下来思考一下，Example本质上也是一个普通的函数，为什么它可以记住之前的状态？

