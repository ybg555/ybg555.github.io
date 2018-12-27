# pager-helper
列表接口请求 API 逻辑封装，主要搭配类似 pager-grid 的数据组件使用

## 代码演示
依赖
* Element 2.x
* Lodash

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
    <!-- pager-helper 拿到的数据用于下面的数据展示组件（pager-grid 是一个表格+分页组合版的数据组件）-->
    <hm-pager-grid
      row-key="tableComment"
      :data="helperData.tableList"
      :page="helperData.page"
      @size-change="helperData.onSizeChange"
      @current-change="helperData.onPageChange">
      <el-table-column prop="payMemo" label="调整备注" align="center"></el-table-column>
    </hm-pager-grid>
  </template>
</hm-pager-helper>
```

使用地址栏参数
```html
<hm-pager-helper
  ref="customer"
  method="get"
  api="api/agaccounttrading/list"
  :useQuery="true"
  :page-size="10"
  :reqPageName="{currPage: 'page', size: 'limit'}"
  :resKeysName="{ data: 'data', list: 'data.list', total: 'data.totalCount', totalPage: 'data.totalPage'}"
  @refresh-page="onRefreshList">
  <template slot-scope="helperData">
    <!-- pager-helper 拿到的数据用于下面的数据展示组件（pager-grid 是一个表格+分页组合版的数据组件）-->
    <hm-pager-grid
      row-key="tableComment"
      :data="helperData.tableList"
      :page="helperData.page"
      @size-change="helperData.onSizeChange"
      @current-change="helperData.onPageChange">
      <el-table-column prop="payMemo" label="调整备注" align="center"></el-table-column>
    </hm-pager-grid>
  </template>
</hm-pager-helper>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| method | 请求方法 |  String | － | get |
| api | 接口地址 |  String | － |  |
| initRequest | 初始化时是否发送第一次请求 |  Boolean | － | true |
| useQuery | 是否启用地址栏的 query 参数 |  Boolean | － | false |
| pageSize | 分页size |  Number | － | 10 |
| reqPageName | 请求分页的参数名 |   Object | － | { currPage: 'page', size: 'pageSize' } |
| params | 其他请求业务参数 |   Object | － | null |
| resKeysName | 返回的数据结构字段名 |   Object | － | { data: 'data', list: 'data.list', total: 'data.total', totalPage: 'data.pages' } |
| beforeRequest | 请求前的句柄函数 |  Function | － | - |
| afterResponse | 返回后句柄函数 |  Function | － | - |
| beforeRefreshRoute | 路由更新前的句柄函数 |  Function | － | - |

## 事件
| 事件名 | 说明 | 回调参数|
|-----|:----------|:------|
| change-current | 更改当前页码时触发 |  选中的值 |
| change-size | 更改页码尺寸时触发 |  选中的值 |
| refresh-page | 分页信息 | - |
| refresh-list | 列表数据 |  - |

