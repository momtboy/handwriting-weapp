# handwriting-weapp
微信小程序Canvas手写板(use canvas in weapp for user signature)

![demo](https://github.com/tclyjy/handwriting-weapp/blob/master/images/handwriting.gif?raw=true)

工作中公司业务需要的微信小程序用户签字功能
准备将其组件化，并加强功能性开发，优化渲染逻辑

## 组件
将components/handwriting  引入小程序中

要使用的页面 index.wxml
```html
<import src="../../components/handwriting/handwriting.wxml" />
<View>
  <template is="handwriting"></template>
</View>
```

使用JS index.js
```js
 onLoad: function (options) {
    this.handwriting = new Handwriting(this, {
      lineColor: this.data.lineColor,
      slideValue: this.data.slideValue,
    })
  },

  // 初始化需传入两个参数 
  // lineColor  字体颜色 默认#1A1A1A 
  // slideValue 字体粗细 默认50（内置 0，25，50, 75, 100 5档粗细）

  /**
   *   example:
   *   this.handwriting = new Handwriting(this, {
        lineColor: '#1A1A1A',
        slideValue: 50,
      })
   */
   
   // 两个内置函数
   this.handwriting.selectColorEvent(color);   // 传入颜色参数 改变字体颜色
   this.handwriting.selectSlideValue(slideValue);  // 传入粗细参数 0,25,50,75,100 改变字体粗细
```


## 更新计划
1. 组件化
2. 优化setData过于频繁照成的渲染延迟
3. 增加笔迹样式