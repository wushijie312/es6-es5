# 简介

> es6转换成es5

## 安装
```
cnpm i babel-cli --save   //es6打包成es6文件但是没有实现转成es5   babel ./src/index.js -o ./dist/index.js
cnpm i babel-preset-es2015 --save //实现es6转换成es5 打包还是不行   原因是安装了但是没有使用新建个.babelrc文件 配置成如下代码

{
    "presets": ["es2015"],
    "plugins": []
}
//再次执行就实现 babel ./src/index.js -o ./dist/index.js  转换了
```



#  使用 npm run serve 打包

//在package.json 文件中的scripts中新加一行 
```
 "scripts": {
    "build" :"babel src/index.js -o dist/index.js"

  },
```
