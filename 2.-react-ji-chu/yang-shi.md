# 样式

## 样式中的像素值

{% hint style="info" %}
**Tips**：React 会自动对 width、height 等属性添加 px。
{% endhint %}

```jsx
// Result style: '10px'
<div style={{ height: 10 }}>
  Hello World!
</div>

// Result style: '10%'
<div style={{ height: '10%' }}>
  Hello World!
</div>
```

{% hint style="warning" %}
**注意**：有些属性除了支持 px 为单位的像素值，还支持数字直接作为值，此时 React 并不添加 px，如 lineHeight，[完整列表](https://github.com/facebook/react/blob/4131af3e4bf52f3a003537ec95a1655147c81270/src/renderers/dom/shared/CSSProperty.js#L15-L59)。
{% endhint %}

## classnames 库的使用

该库主要用来给组件动态设置 className。

```jsx
import cx from 'classnames';
<div className={cx(
  'header-left',  // 最简单的类名
  {loading: props.loading })}, // 属性值为true，才生成类名
  `button-${props.color}`,  // 传入属性生成动态类名，注意不传也会生成
  {[`ts-${props.type}`]: props.type} // 属性值为true，才生成动态类名
/>
```

{% hint style="danger" %}
**强制**：不要使用类似 clazz 等方式传入父组件的类名，直接将 className 挂到 props 上往下传递，通过 cx 或 className 动态取都可以。
{% endhint %}

{% hint style="success" %}
**推荐**：库名用 cx 来命名，防止与 className 发生歧义。
{% endhint %}

## cssModules

cssModules 没有在项目中实际应用，暂不做介绍。

