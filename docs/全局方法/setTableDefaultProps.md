# 设置表格默认属性

## setTableDefaultProps

可以通过 `setTableDefaultProps` 设置一些表格的默认属性，现在你可以跑到其它表格页面，会发现已经没有了边框。

```tsx
import React from 'react'
import { AySearchTable, setTableDefaultProps } from 'amiya'
import { listApi } from '../api'
import 'antd/dist/antd.min.css'

setTableDefaultProps({
  bordered: false
})

const fields: Array<AySearchTableField> = [
  {
    title: '姓名',
    key: 'cname',
    search: {}
  },
  {
    title: '英文名',
    key: 'name',
    search: {}
  }
]

export default function Demo() {
  return <AySearchTable title="取消全局表格的边框" api={listApi} fields={fields} />
}
```
