# QRCode.js
QRCode.js is javascript library for making QRCode. QRCode.js supports 微信小程序.
QRCode.js has no dependencies.

使用微信 `wx.createOffscreenCanvas` api 离线绘制二维码, 使用 `toDataURL` 方法转换为 `DataURL` 配合 `image` 标签使用.
避免使用 `canvas` 标签, `canvas` 标签为原生标签, 使用起来限制和兼容性不友好.

## Basic Usages

- 复制文件

复制 `qrcode.js` 文件到小程序 `utils` 目录中.

- index.js

```js
import QRCode from '../../utils/qrcode';

Page({
  data: {
    qrcodeDataUrl: '',
  },
  onLoad() {
    const qrcode = new QRCode({
      text : 'http://www.dotcoo.com',
      width : 600,
      height : 600
    });
    this.setData({
      qrcodeDataUrl: qrcode.toDataURL(),
    });
  },
});
```

- index.wxml

```html
<image src="{{qrcodeDataUrl}}" class="canvas" />
```

- index.wxss

```css
.canvas {
  width: 600rpx;
  height: 600rpx;
  border: 1rpx solid #ccc;
}
```

## Manual

[https://github.com/davidshimjs/qrcodejs](https://github.com/davidshimjs/qrcodejs)

## License
MIT License

## Contact
twitter @davidshimjs

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/davidshimjs/qrcodejs/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

