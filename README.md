# vue3-vw

参考大漠的[如何在Vue项目中使用vw实现移动端适配](https://www.w3cplus.com/mobile/vw-layout-in-vue.html)，对vue-cli3项目对postCSS部分进行配置，



配置文件在postcss.config.js中，配置如下



```javascript
module.exports = {
  plugins: [
    require('postcss-import'),
    require('postcss-url'),
    require('postcss-aspect-ratio-mini'),
    require('postcss-write-svg')({ utf8: false }),
    require('postcss-cssnext'),
    require('postcss-px-to-viewport')({
      viewportWidth: 750, // 视窗的宽度，对应的是我们设计稿的宽度，一般是750
      viewportHeight: 1334, // 视窗的高度，根据750设备的宽度来指定，一般指定1334，也可以不配置著作权归作者所有。
      unitPrecision: 3, // 指定`px`转换为视窗单位值的小数位数（很多时候无法整除）著作权归作者所有。
      viewportUnit: 'vw', // 指定需要转换成的视窗单位，建议使用vw
      selectorBlackList: ['.ignore', '.hairlines'], // 指定不转换为视窗单位的类，可以自定义，可以无限添加,建议定义一至两个通用的类名
      minPixelValue: 1, // 小于或等于`1px`不转换为视窗单位，你也可以设置为你想要的值著作权归作者所有。
      mediaQuery: false // 允许在媒体查询中转换`px`
    }),
    require('cssnano')({
      preset: "advanced", 
      autoprefixer: false, 
      "postcss-zindex": false
    }),
  ]
}

```



------

#### 学习使用了以下几个插件

- [ ] **cssnano**   CSS的新特性，可用来代替sass、less预处理器
- [x] **postcss-px-to-viewport**  将px单位转化为vw单位
- [x] **postcss-aspect-ratio-mini**  用来处理容器的宽高比
- [ ] **postcss-write-svg**  用来处理移动端1px问题
- [ ] **postcss-import**  解决@import 引入路径问题
- [ ] **postcss-url**  处理图片、字体等文件的引入路径问题
- [x] **autoprefixer**   自动处理浏览器前缀 