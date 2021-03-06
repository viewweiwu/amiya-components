# AyDialog

![amiya AyDialog](https://misc.hzzcckj.cn/upload/image/202011/ac64d2e7e400000.png)

## 基础示例

```tsx
import React, { useState } from 'react'
import { AyDialog, AyButton } from 'amiya'
import 'antd/dist/antd.min.css'

export default function Demo() {
  const [visible, setVisible] = useState<boolean>(false)
  return (
    <div>
      <AyButton type="primary" onClick={() => setVisible(true)}>
        打开弹窗
      </AyButton>
      <AyDialog title="メセージ" visible={visible} setVisible={setVisible} onConfirm={() => alert('确认')}>
        <p>ドクター、終わってない仕事がたくさんありますから。まだ休んじゃダメですよ。</p>
      </AyDialog>
    </div>
  )
}
```

## Drawer 模式

```tsx
import React, { useState } from 'react'
import { AyDialog, AyButton } from 'amiya'
import 'antd/dist/antd.min.css'

export default function Demo() {
  const [visible, setVisible] = useState<boolean>(false)
  return (
    <div>
      <AyButton type="primary" onClick={() => setVisible(true)}>
        打开弹窗
      </AyButton>
      <AyDialog drawer title="メセージ" visible={visible} setVisible={setVisible} onConfirm={() => alert('确认')}>
        <p>ドクター、終わってない仕事がたくさんありますから。まだ休んじゃダメですよ。</p>
      </AyDialog>
    </div>
  )
}
```

## 元素插槽

```tsx
import React, { useState } from 'react'
import { AyDialog, AyButton } from 'amiya'
import 'antd/dist/antd.min.css'

export default function Demo() {
  const [visible, setVisible] = useState<boolean>(false)
  return (
    <div>
      <AyButton type="primary" onClick={() => setVisible(true)}>
        打开弹窗
      </AyButton>
      <AyDialog
        width={800}
        titleBefore={<AyButton>标题之前</AyButton>}
        titleAfter={<AyButton>标题之后</AyButton>}
        cancelBefore={<AyButton>关闭之前</AyButton>}
        cancelAfter={<AyButton>关闭之后</AyButton>}
        confirmBefore={<AyButton>确认之前</AyButton>}
        confirmAfter={<AyButton>确认之后</AyButton>}
        title="底部元素添加"
        visible={visible}
        setVisible={setVisible}
        onConfirm={() => alert('确认')}
      >
        <p>头部有 2 个放置元素。</p>
        <p>底部有 4 个位置可以放置元素。</p>
      </AyDialog>
    </div>
  )
}
```

## 参数

| 参数名         | 说明                           | 参数类型                            | 默认值 |
| -------------- | ------------------------------ | ----------------------------------- | ------ |
| title          | 标题                           | ReactNode                           | -      |
| visible        | 是否展示                       | boolean                             | -      |
| setVisible     | 自动关闭弹窗时，可以传递此参数 | Dispatch<SetStateAction<boolean\>\> | -      |
| onConfirm      | 确认按钮事件监听               | () => void                          | -      |
| loading        | 是否正在加载                   | boolean                             | -      |
| footer         | 自定义底部按钮                 | ReactNode                           | -      |
| width          | 弹窗宽度                       | number                              | -      |
| drawer         | 是否侧边展示                   | boolean                             | false  |
| titleBefore    | 标题前置元素                   | ReactNode                           | -      |
| titleAfter     | 标题后置元素                   | ReactNode                           | -      |
| confirmVisible | 确定按钮是否展示               | boolean                             | true   |
| cancelVisible  | 关闭按钮是否展示               | boolean                             | true   |
| confirmText    | 确定按钮文字                   | string                              | '确定' |
| cancelText     | 关闭按钮文字                   | string                              | '关闭' |
| confirmProps   | 确认按钮属性                   | AyButtonProps                       | {}     |
| cancelProps    | 关闭按钮属性                   | AyButtonProps                       | {}     |
| confirmBefore  | 确定按钮前置元素               | ReactNode                           | -      |
| confirmAfter   | 确定按钮后置元素               | ReactNode                           | -      |
| cancelBefore   | 关闭按钮前置元素               | ReactNode                           | -      |
| cancelAfter    | 关闭按钮后置元素               | ReactNode                           | -      |
| className      | 样式                           | -                                   | -      |

### 样式设置注意点

```html
// 注意样式设置时，样式会在外层，如果想要设置 body 里的元素样式，请尝试这样写。

<AyDialog className="dialog-class"> </AyDialog>
<AyDialog className="drawer-class" drawer> </AyDialog>

<style>
  .dialog-class .ant-modal-body {
    // 这里设置弹窗样式
  }
  .drawer-class .ant-drawer-body {
    // 这里设置侧边弹窗样式
  }
</style>
```

[1]: https://ant-design.gitee.io/components/modal-cn/#API
