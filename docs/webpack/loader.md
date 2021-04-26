<!--
 * @Author: tangdaoyong
 * @Date: 2021-04-26 11:20:18
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-04-26 14:04:03
 * @Description: webpack loader
-->
# webpack加载器

## 介绍

[webpack加载器](https://webpack.docschina.org/api/loaders/)
[Webpack Loader 高手进阶(一)](https://segmentfault.com/a/1190000018450503)
compiler和compilation都继承于Tapable

webpack的插件是基于Tapable的，Tapable允许你添加和应用插件到javascript模块中，类似于 NodeJS的EventEmitter，可以被继承和mixin到其他模块中，详情见官网[Tapable]()

## loader的使用方式

一般loader的使用方式分为三种：

### 1.在配置文件webpack.config.js中配置

module.exports = {
  module: {
    rules: [
      {
        test: /\.txt$/,
        use: 'raw-loader'
      }
    ]
  }
}
### 2.通过命令行参数方式

webpack --module-bind 'txt=raw-loader'
### 3.通过内联使用

import txt from 'raw-loader!./file.txt';

## workflow

![webpack-workflow](./images/webpack-workflow.jpeg)

## loader流程

![loader流程](./images/loader流程.jpeg)

## loader和gulp

[loader和gulp](https://zhuanlan.zhihu.com/p/28245984)