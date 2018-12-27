# pager-grid
表格 + 分页的组合版，一般搭配 pager-helper 组件使用

## 示例图
![](../.vuepress/public/images/pager-grid.jpg)

## 代码演示
依赖
* Element 2.x

基本用法
```html
<hm-pager-helper
  ref="customer"
  method="get"
  api="api/agaccounttrading/list"
  :page-size="10"
  :reqPageName="{currPage: 'page', size: 'limit'}"
  :resKeysName="{ data: 'data', list: 'data.list', total: 'data.totalCount', totalPage: 'data.totalPage'}"
  @refresh-page="onRefreshList">
  <template slot-scope="helperData">
    <!--搭配上面的 pager-helper 一起使用-->
    <hm-pager-grid
      row-key="tableComment"
      :data="helperData.tableList"
      :page="helperData.page"
      @size-change="helperData.onSizeChange"
      @current-change="helperData.onPageChange">
      <el-table-column prop="payMemo" label="调整备注" align="center"></el-table-column>
    </hm-pager-grid>
  </template>
</hm-pager-grid>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| rowKey | 对应表格的 row-key |  String、Function | － | id |
| data | 表格的数据 |  Array | － |  |
| height | 表格的 height 属性 |  String, Number  | － |  |
| maxHeight | 表格的 max-height 属性 |  String, Number | － |  |
| border | 表格显示边框 |   Boolean  | 选传 | true |
| stripe | 斑马纹 |   Boolean  | 选传 | true |
| highlight | 行选中是否高亮 |   Boolean  | 选传 | false |
| paginationLayout | pagination 分页的 UI 格式 |  String | － | 'sizes, prev, pager, next' |
| page | 分页数据 |   Object | － | { currPage: 1, size: 1, total: 0 } |
| pageSizes | 分页单位 |   Array | － | [10, 20, 50, 100] |

## 事件
| 事件名 | 说明 | 回调参数|
|-----|:----------|:------|
| select | 	当用户手动勾选数据行的 Checkbox 时触发的事件 |  selection, row |
| select-all | 当用户手动勾选全选 Checkbox 时触发的事件 |  selection |
| selection-change| 当选择项发生变化时会触发该事件 | selection |
| sort-change| 当表格的排序条件发生变化的时候会触发该事件 |  { column, prop, order } |
| size-change | pageSize 改变时会触发 | 每页条数 |
| current-change | currentPage 改变时会触发 | 当前页 |
| row-click | 点击行时会触发 | 当前行row |

