## gnh-activity-modal
> 活动弹窗

### 使用
1. 安装
```
npm install gnh-activity-modal -S
// or
yarn add gnh-activity-modal
```
2. 引入
```
import GnhActivityModal from 'gnh-activity-modal'
...

components: {
    [GnhActivityModal.name]: GnhActivityModal
  }
...
```
3. 使用
```
<gnh-activity-modal
  :closeBtn="require('./assets/close-btn.png')"
  :topImg="require('./assets/reward_mask.png')"
  :centerIcon="require('./assets/reward_success_icon.png')"
   @onHide="onHide"
  ref="modal"
  @onClick="clickHandle"
  />

// methods
 methods: {
    clickHandle (e) {
      this.$refs.modal.$hide()
      // 或者使用 this.$refs.modal.toggle()
    },
    onHide () {
      console.log('hide')
    }
  },

```

### props
|属性|说明|类型|默认值|
|---|----|----|----|
|closeBtn|关闭按钮图片|使用require加载图片资源|无|
|topImg|弹窗顶部图片|使用require加载图片资源|无|
|centerIcon|弹窗中间位置的图片|使用require加载图片资源|无|
|centerIconWidth|弹窗中间位置的图片的宽度|String Number|82|
|contentTitle|主标题|String|确认加速该订单吗|
|contentSubTitle|副标题|String|确认后不可修改|
|btnText|按钮文案|String|确认|
|hasMask|是否有遮罩|Boolean|true|
|maskClosable|遮罩点击是否关闭弹窗|Boolean|true|
|onClick|点击按钮触发的事件|Function|无|

### slot 插槽
|slot-name|说明|默认值|
|---|----|----|
|close-btn|关闭按钮插槽|closeBtn图片|
|modal-center|中间内容插槽|centerIcon图片icon|
|modal-bottom|弹窗底部插槽|确认按钮|

### 方法
|方法名|说明|示例|
|---|----|----|
|toggle|切换弹窗状态|`this.$refs.modal.toggle()`|
|$show|展示弹窗|`this.$refs.modal.$show()`|
|$hide|关闭弹窗|`this.$refs.modal.$hide()`|


### 通知
|方法名|说明|示例|
|---|----|----|
|onHide|弹窗关闭时候触发||
