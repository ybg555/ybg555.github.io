# text-cell
列表项，左边 title、右边内容的格式；一些详情页用的比较多。

## 示例图
![](../.vuepress/public/images/text-cell.jpg)

## 代码演示
依赖
* Element 2.x

基本用法
```html
<hm-text-cell :labelWidth="150" label="经营地址：" text="长沙岳麓区胜利者同盟大厦"></hm-text-cell>
```
slot 用法
```html
<hm-text-cell :labelWidth="150" label="服务时长：" text="5">
  <span slot="prefix">剩余</span>
  <span>天</span>
</hm-text-cell>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| label | 标题 |  String | － | - |
| labelWidth | 标题宽度 |  Number | － | 120 |
| text | 内容 |  String | － | - |

## slot（定制）
* name="prefix"
* 默认

