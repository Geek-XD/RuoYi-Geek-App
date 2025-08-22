# uni-app 二维码生成器

改自作者诗小柒的tki-qrcode二维码生成器

### 作者：Dftre

1. H5、微信小程序、支付宝小程序、APP，其它平台的小程序没有测试
2. 使用canvas生成
3. 可设置二维码背景色，前景色，角标色
4. 可设置二维码logo

### 使用方法

在 `template` 中使用

```javascript
<view class="qrimg">
    <geek-qrcode
    ref="qrcode"
    :cid="cid"
    :val="val"
    :size="size"
    :unit="unit"
    :background="background"
    :foreground="foreground"
    :pdground="pdground"
    :icon="icon"
    :iconSize="iconsize"
    :lv="lv" 
    :onval="onval"
    :loadMake="loadMake"
    :usingComponents="usingComponents"
    :showLoading="showLoading"
    :loadingText="loadingText"
    @result="qrR" />
</view>
```

### 属性

| 属性名          |  类型  |      默认值      | 可选值 | 说明                                                                                                |
| :-------------- | :-----: | :---------------: | :----: | :-------------------------------------------------------------------------------------------------- |
| cid             | String | tki-qrcode-canvas |        | canvasId，页面存在多个二维码组件时需设置不同的ID                                                    |
| size            | Number |        200        |        | 生成的二维码大小                                                                                    |
| unit            | String |        upx        |   px   | 大小单位尺寸                                                                                        |
| show            | Boolean |       true       |        | 默认使用组件中的image标签显示二维码                                                                 |
| val             | String |      二维码      |        | 要生成的内容                                                                                        |
| background      | String |      #000000      |        | 二维码背景色                                                                                        |
| foreground      | String |      #ffffff      |        | 二维码前景色                                                                                        |
| pdground        | String |      #ffffff      |        | 二维码角标色                                                                                        |
| icon            | String |                  |        | 二维码图标URL（必须是本地图片，网络图需要先下载至本地）                                             |
| iconSize        | Number |        40        |        | 二维码图标大小（注意此大小不会跟随二维码size 动态变化，设置时需要注意大小，不要太大，以免无法识别） |
| lv              | Number |         3         |        | 容错级别（一般不用设置）                                                                            |
| onval           | Boolean |       false       |        | 监听val值变化自动重新生成二维码                                                                     |
| loadMake        | Boolean |       false       |        | 组件初始化完成后自动生成二维码，val需要有值                                                         |
| usingComponents | Boolean |       true       | false | 是否使用了自定义组件模式（主要是为了修复非自定义组件模式时 v-if 无法生成二维码的问题）              |
| showLoading     | Boolean |       true       | false | 是否显示loading                                                                                     |
| loadingText     | String |   二维码生成中   |        | loading文字                                                                                         |

### 方法

| 方法名       | 参数 | 默认值 | 说明                                                |
| :----------- | :--: | :----: | :-------------------------------------------------- |
| _makeCode()  |      |        | 生成二维码                                          |
| _clearCode() |      |        | 清空二维码（清空二维码会触发result回调 返回值为空） |
| _saveCode()  |      |        | 保存二维码到图库                                    |

### 事件

| 事件名 |             返回值             |                                    说明 |
| :----- | :----------------------------: | --------------------------------------: |
| result | 生成的图片base64或图片临时地址 | 返回二维码路径 注：_clearCode()后返回空 |

### 感谢

[uni-app](https://uniapp.dcloud.io/ "uni-app")
[qrcode](https://github.com/aralejs/qrcode "qrcode")
tki-qrcode
