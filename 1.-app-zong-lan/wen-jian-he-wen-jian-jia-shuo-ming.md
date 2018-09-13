# 命名规范

## 文件夹命名

{% hint style="success" %}
**推荐**：React 组件的文件夹命名都是 **大驼峰 + 单数**，其他文件夹都是 **小驼峰 + 复数**。
{% endhint %}

示例：

```text
Header
Button
components
widgets
utils
states
apis
libs
```

## 文件命名

{% hint style="success" %}
**推荐**：文件命名都是 **小驼峰**，单复数看情形。
{% endhint %}

{% hint style="success" %}
**推荐**：大部分 js 文件需要加上 **类型后缀**，以便快速搜索文件和在 IDE 多个标签中能快速区分。
{% endhint %}

类型后缀包括：

```text
xxx.presentational.js
xxx.container.js
xxx.widget.js
xxx.action.js
xxx.middleware.js
xxx.reducer.js
xxx.selector.js
xxx.api.js
xxx.util.js
```

示例：

```text
index.js
router.js
creatDocument.action.js
errorLog.middleware.js
```

## 方法/变量命名

{% hint style="success" %}
**推荐**：方法名都是 **小驼峰**，单复数看情形。
{% endhint %}

{% hint style="success" %}
**推荐**：变量名除常量外都是 **小驼峰**，单复数看情形。
{% endhint %}

{% hint style="success" %}
**推荐**：常量名都是 **全大写字母 + 下划线分隔**，单复数看情形。
{% endhint %}

示例：

```text
UNIFIED_STATES
LINES_SET_FILTER
```

