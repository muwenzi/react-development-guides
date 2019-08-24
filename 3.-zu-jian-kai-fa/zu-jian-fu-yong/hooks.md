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

### 假如一个组件有多个状态值怎么办？

首先，useState是可以多次调用的，所以我们完全可以这样写：

```javascript
function ExampleWithManyStates() {
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
}
```

其次，useState接收的初始值没有规定一定要是string/number/boolean这种简单数据类型，它完全**可以接收对象或者数组作为参数**。最后，react也给我们提供了一个`useReducer`的hook，如果你更喜欢redux式的状态管理方案的话。

{% hint style="warning" %}
**注意**：之前我们的`this.setState`做的是**合并状态**后返回一个新状态，而`useState`是直接**替换**老状态后返回新状态。
{% endhint %}

从`ExampleWithManyStates`函数我们可以看到，`useState`无论调用多少次，相互之间是独立的。这一点至关重要。为什么这么说呢？

其实我们看hook的“形态”，有点类似之前被官方否定掉的Mixins这种方案，都是提供一种“插拔式的功能注入”的能力。而mixins之所以被否定，是因为**Mixins机制是让多个Mixins共享一个对象的数据空间**，这样就很难确保不同Mixins依赖的状态不发生冲突。

而现在我们的hook，一方面它是直接用在function当中，而不是class；另一方面每一个hook都是相互独立的，**不同组件调用同一个hook也能保证各自状态的独立性。**这就是两者的本质区别了。

### React是怎么保证多个useState的相互独立的？

还是看上面给出的`ExampleWithManyStates`例子，我们调用了三次`useState`，每次我们传的参数只是一个值（如42，‘banana’）_，_我们根本没有告诉react这些值对应的key是哪个，那react是怎么保证这三个useState找到它对应的state呢？

{% hint style="info" %}
**Tips**：React是根据`useState`出现的顺序来定的。
{% endhint %}

我们具体来看一下：

```javascript
  //第一次渲染
  useState(42);  //将age初始化为42
  useState('banana');  //将fruit初始化为banana
  useState([{ text: 'Learn Hooks' }]); //...

  //第二次渲染
  useState(42);  //读取状态变量age的值（这时候传的参数42直接被忽略）
  useState('banana');  //读取状态变量fruit的值（这时候传的参数banana直接被忽略）
  useState([{ text: 'Learn Hooks' }]); //...
```

假如我们改一下代码：

```javascript
let showFruit = true;
function ExampleWithManyStates() {
  const [age, setAge] = useState(42);
  
  if(showFruit) {
    const [fruit, setFruit] = useState('banana');
    showFruit = false;
  }
 
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
}
```

这样一来：

```javascript
  //第一次渲染
  useState(42);  //将age初始化为42
  useState('banana');  //将fruit初始化为banana
  useState([{ text: 'Learn Hooks' }]); //...

  //第二次渲染
  useState(42);  //读取状态变量age的值（这时候传的参数42直接被忽略）
  // useState('banana');  
  useState([{ text: 'Learn Hooks' }]); //读取到的却是状态变量fruit的值，导致报错
```

{% hint style="danger" %}
**强制**：React规定我们必须把hooks写在函数的最外层，不能写在`ifelse`等条件语句当中，来确保hooks的执行顺序一致。
{% endhint %}

