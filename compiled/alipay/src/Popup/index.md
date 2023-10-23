---
nav:
  path: /components
group:
  title: 反馈
  order: 12
toc: 'content'
---

# Popup 弹出层
从屏幕滑出或弹出一块自定义内容区
## 何时使用
用于展示弹窗、信息提示、选择输入、切换等内容，支持多个弹出层叠加展示

## 代码示例
<code src='pages/Popup/index'></code>

## API

| 属性 | 说明 | 类型 | 默认值 |
| -----|-----|-----|-----|
| animation | 是否开启过渡动画 | boolean | true |  
| animationType | 动画类型，可选`transform` `position`，默认使用`transform`动画性能更好。但当弹窗内部存在fixed定位或者picker-view元素时可能存在样式问题，可切换为`position`解决 | string | `transform` |  
| className | 类名 | string | - | 
| destroyOnClose | 不可见时卸载内容 | boolean | false | 
| duration | 过渡动画时长，单位毫秒 | number | 300 | 
| height | 高度，在 position 为 `top` 或 `bottom` 时使用，单位px。可选，不传时根据内容区高度自适应。 | number | - | 
| maskClassName | 蒙层的类名 | string | - | 
| maskStyle | 蒙层的样式 | string | - | 
| position | 弹窗布局，可选`top` `bottom` `left` `right` | string | `bottom` | 
| showMask | 是否展示蒙层 | boolean | true |
| style | 样式 | string | - |
| visible |  是否显示 | boolean | false | 
| width | 宽度, 在 position 为 `left` 或 `right` 时使用，单位px | number | - | 
| zIndex | 弹窗层级 | number | 998 | 
| onClose | 点击蒙层关闭，触发回调 | () => void |

## FAQ
### Popup打开后，蒙层后面的页面能滚动
阻止蒙层后页面滚动目前IDE和模拟器不生效，请在真机调试

### Popup内部元素需要支持滚动
弹窗内需要滚动，请使用scroll-view组件，并添加属性
```html
<popup height="{{ 250 }}" visible="{{ visible }}">
  <scroll-view scroll-y disable-lower-scroll="out-of-bounds" disable-upper-scroll="out-of-bounds">
    ...你的内容
  </scroll-view>
</popup>
```




