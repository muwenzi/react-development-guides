# 5. 路由管理

{% embed data="{\"url\":\"http://reacttraining.cn/web/example/basic\",\"type\":\"link\",\"title\":\"React Router: 用于 React.js 的声明式路由库\",\"description\":\"Learn once, Route Anywhere\",\"icon\":{\"type\":\"icon\",\"url\":\"http://reacttraining.cn/apple-touch-icon.png\",\"width\":180,\"height\":180,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"http://reacttraining.cn/react-square.png\",\"width\":562,\"height\":562,\"aspectRatio\":1}}" %}

React Router被拆分成三个包：`react-router`,`react-router-dom`和`react-router-native`。`react-router`提供核心的路由组件与函数。其余两个则提供运行环境（即浏览器与react-native）所需的特定组件。

进行网站（将会运行在浏览器环境中）构建，我们应当安装`react-router-dom`。`react-router-dom`暴露出`react-router`中暴露的对象与方法，它会自动安装 `react-router` ，因此你只需要安装并引用`react-router-dom`即可。

