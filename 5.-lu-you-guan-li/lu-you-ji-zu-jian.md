# Router

Router 翻译过来即“`路由器`“，对于 Web 项目，存在 `<BrowserRouter>`与`<HashRouter>`两种组件。当存在服务器来管理动态请求时，使用 `<BrowserRouter>` 组件，而 `<HashRouter>` 被用于静态网站。

{% hint style="success" %}
**推荐**：通常推荐选择 &lt;BrowserRouter&gt; ，但如果你的网站仅用来呈现静态文件，那么 &lt;HashRouter&gt; 将会是一个好选择。
{% endhint %}

## 渲染 &lt;Router&gt;

{% hint style="warning" %}
**注意**：&lt;Router&gt; 组件无法接受两个及以上的子元素。
{% endhint %}

基于这种限制的存在，创建一个`<App>`组件来渲染应用其余部分是一个有效的方法（对于服务端渲染，将 App 从 &lt;Router&gt; 中分离也是重要的）。

```jsx
import { BrowserRouter } from 'react-router-dom'
ReactDOM.render((
  <BrowserRouter>
    <App />
  </BrowserRouter>
), document.getElementById('root'))
```

## 历史 \(History\)

每个 &lt;Router&gt; 都会创建一个 history 对象并用其保持追踪当前`location`，并且在有变化时对页面进行重新渲染。这个 history 对象保证了Router 提供的其他组件的可用性。

{% hint style="warning" %}
**注意**：组件必须在 Router 内部渲染。
{% endhint %}

```jsx
import { Router } from 'react-router-dom'
import createBrowserHistory from 'history/createBrowserHistory'

const history = createBrowserHistory()

<Router history={history}>
  <App/>
</Router>
```

