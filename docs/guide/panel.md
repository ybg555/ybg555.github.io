# panel
面板，页面的基础结构布局。包含标题和内容2块区域。

## 示例图
![](/images/panel.jpg)

## 代码演示
依赖
* Element 2.x

基本用法
```html
<hm-panel title="标题" subTitle="副标题">
  <div>内容</div>
</hm-panel>
```
slot 用法
```html
<hm-panel title="标题" subTitle="副标题" :showIcon="false">
  <div slot="header-right">
    <el-button type="primary" size="small">按需传入</el-button>
  </div>

  <div>内容</div>
</hm-panel>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| title | 标题 |  String | － | - |
| subTitle | 副标题 |  String | － |  |
| showIcon | 显示 icon |  Boolean | － | true |
| icon | 显示 icon |  String | － | el-icon-news |

## slot
* name="header-right"
* 默认（内容）

