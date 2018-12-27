# multi-cascader
级联选择器 + 多选菜单，基于 Cascader + Select 组件

## 示例图
![](../.vuepress/public/images/multi-cascader1.jpg)
![](../.vuepress/public/images/multi-cascader2.jpg)

## 代码演示
依赖
* Element 2.x

基本用法
```html
<hm-multi-cascader
  title="请选择开票范围"
  :getLast="true"
  @change="onChange"
  :selectVal="['layout', 'button']"
  :cascaderOptions="cascaderOptions">
</hm-multi-cascader>
```
```js
// cascaderOptions 入参
cascaderOptions: [
  {
    value: 'zujian',
    label: '组件',
    children: [
    {
      value: 'basic',
      label: 'Basic',
      children: [{
        value: 'layout',
        label: 'Layout 布局'
      }, {
        value: 'color',
        label: 'Color 色彩'
      }, {
        value: 'typography',
        label: 'Typography 字体'
      }, {
        value: 'icon',
        label: 'Icon 图标'
      }, {
        value: 'button',
        label: 'Button 按钮'
      }]
    }, {
      value: 'others',
      label: 'Others',
      children: [{
        value: 'dialog',
        label: 'Dialog 对话框'
      }, {
        value: 'tooltip',
        label: 'Tooltip 文字提示'
      }, {
        value: 'popover',
        label: 'Popover 弹出框'
      }]
    }]
  }, {
    value: 'ziyuan',
    label: '资源',
    children: [{
      value: 'axure',
      label: 'Axure Components'
    }, {
      value: 'sketch',
      label: 'Sketch Templates'
    }, {
      value: 'jiaohu',
      label: '组件交互文档'
    }]
  }],
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| title | 弹窗的标题 |  String | － | - |
| getLast | 选中值格式类似 A/B/C 取 C |  Boolean | － | false |
| selectVal | 选中值 |  Array | － | [] |
| cascaderOptions | 级联组件 options |  Array | － | [] |
| cascaderProps | 级联组件属性的 key |  Array | － | { value: 'value', label: 'label' } |
| selectDisabled | 是否禁用 |  Boolean | － |  false |
| allSelected | 是否启用全选 |  Boolean | － |   true |

## 事件
| 事件名 | 说明 | 回调参数|
|-----|:----------|:------|
| change | 选中值发生变化时 |  选中的值 |


