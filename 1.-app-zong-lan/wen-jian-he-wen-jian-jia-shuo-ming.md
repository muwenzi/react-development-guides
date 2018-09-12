# 文件和文件夹说明

### libs

放app里面用到的一些公共方法/库

### AppName.browser.js

App的入口文件，主要包括创建Store、初始化状态、挂载react app，连接状态树等。

### AppName.server.js

可以对后端的多个请求做二次封装处理，也可以做一些跨域处理等。

### AppName.webpack.less

app样式的入口文件

示例：

```javascript
@import '~runtime'; 
@import url('./src/icons/icons.less');

.App {
  @import url('src/ui/Button/index.less');
  @import url('src/ui/ButtonGroup/index.less');
  @import url('src/components/App/index.less');
  @import url('src/components/Footer/index.less');
}
```

### Layout

配合 `manualLayout` 属性为 `true` 的时候使用，是非常基本的和App iframe有关的布局，如果为`false`，App iframe里面会自动加上 、 等这些基础布局。

示例：

```jsx
const Layout = props =>
	<div>
		<header data-ts="TopBar" />
		<Spinner show={props.show} blocking={props.blocking} message={props.message} />
		<main data-ts="Main">
			<div data-ts="MainContent">
				<StickyContainer className="ts-main" style={{ top: 0 }}>
					{props.children}
				</StickyContainer>
			</div>
		</main>
	</div>; 
```

### App

主要是根据不同的Router加载不同的components。
