# pager-card
大盘数据 card 组件

## 示例图
![](../.vuepress/public/images/pager-card.jpg)

## 代码演示
依赖
* Element 2.x

基本用法
```html
<el-col :lg="6" :md="12">
  <hm-pager-card
    title="本月开票金额（元）"
    :content="content"
    :desc="{
      type: 'rate', // rate, process, time, slot
      rate: [ // 选传，和 type 配套
        {
          type: 'top', // bottom
          txt: '月环比',
          unit: '20%',
        }
      ],
      process: 60, // 选传，和 type 配套
      time: { // 选传，和 type 配套
        from: '2018-10-01',
        to: '2019-09-19'
      }
    }"
    :bottom="{label: '申报截至日期', list: [{txt: '12', unit: '月'}, {txt: '15', unit: '日'}]}"
  >
  </hm-pager-card>
</el-col>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| title | 标题 |   String | 必传 | '' |
| tips | 提示语 |   String | 选传 | '' |
| content | 内容 |   String | 必传 | '' |
| bottom | 底部配置 |   Object | 必传 | {label: ''} |
| desc | 描述配置 |   Object | 选传 | {type: ''}，参考上面 demo 中 type 对应字段的值 |

## slot(定制)
```html
<!-- 右边内容 -->
<div slot="cont-right">右边内容</div>

<!-- 描述 -->
<div slot="desc">
  <div class="time">
    <span class="label">111111</span> 至 <span class="label">22222</span>
  </div>
</div>

<!-- 底部 -->
<div slot="bottom">日均开票金额 100元</div>
```