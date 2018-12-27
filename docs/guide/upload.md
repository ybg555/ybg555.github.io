# upload
上传文件、图片。功能支持上传、删除、图片预览和文件下载

## 示例图
![](../.vuepress/public/images/upload-image1.jpg)
![](../.vuepress/public/images/upload-image2.jpg)
![](../.vuepress/public/images/upload-file.jpg)

## 代码演示
依赖
* Element 2.x
* Lodash

上传图片 - 照片墙模式
```html
<hm-upload
  action="/admin/upload"
  fileType="image"
  name="image1"
  :limit="3"
  showType="picture-card"
  tips="文件支持 png、jpg，单张10M内"
  :fileList="uploadList"
  @update-success="handleSuccess"
  @del-success="uploadDelSuccess"
>
</hm-upload>
```

上传图片 - 列表模式
```html
<hm-upload
  action="/admin/upload"
  fileType="image"
  name="image2"
  :limit="3"
  showType="picture"
  tips="文件支持 png、jpg，单张10M内"
  :fileList="uploadList"
  @update-success="handleSuccess"
  @del-success="uploadDelSuccess"
>
</hm-upload>
```

上传文件
```html
<hm-upload
  action="/admin/upload"
  fileType="file"
  name="image3"
  :limit="3"
  tips="文件支持 png、jpg，单张10M内"
  :fileList="uploadList"
  @update-success="handleSuccess"
  @del-success="uploadDelSuccess"
>
</hm-upload>
```

## 参数说明
| 参数 | 说明 | 类型|  可选值 | 默认值 |
|-----|:----------|:------|:------------|:--------|
| action | 服务端接口地址 | String | 必传 | - |
| fileType | 上传文件类型 | String | 必传 | 支持 image,file,video,audio |
| name | 服务端协议字段名 | String | 必传 | - |
| limit | 允许上传数 |  Number | 选传 | 1 |
| fileSize | 允许上传大小 | Number | 选传 | 10M |
| showType | 上传图片时显示的模式 | String | 选传 | picture-card |
| tips | 提示语 | String | 选传（上传图片-照片墙模式 不支持该属性） | - |
| btnOptions | 上传按钮定制 | Object | 选传 | { size: 'mini', text: '上传', showIcon: 'show' } |
| fileList | 编辑模式下的初始数据 | Array | 选传 | [{name: '', url: ''}] |

## 事件
| 事件名 | 说明 | 回调参数|
|-----|:----------|:------|
| before-upload | 上传前 | - |
| update-success | 上传成功 | 文件对象 |
| del-success | 删除成功 | 文件对象 |


