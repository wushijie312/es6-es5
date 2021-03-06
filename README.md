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
# 使用热更新

```

live-server  //全局安装 cnpm i --save live-server 然后执行live-server即可实现热更新

```
#  使用 live-server

//在package.json 文件中的scripts中新加一行 
```
 "scripts": {
    "server": "live-server ./ --port=8081"
  },
```







ES6开发环境搭建（将ES6语法转换为ES5语法）
学习ES6的前置知识：

1、熟练掌握ES5的知识：因为ES6只是ES5的升级，所以你必须对ES5的基本语法达到熟练的程度，如果你还不了解ES5的基本语法，还是脚踏实地地从头开始

2、了解ES6：听说并在工作学习中见过ES6，并了解ES6的用途

 

为什么要搭建ES6开发环境？

为什么不像ES5那样直接写完就完事了，因为许多低版本浏览器并不支持ES6语法，大部分还是支持ES5语法，所以要搭建ES6开发环境，然后放在生产环境中，就是已经做好了上线。

 

1、首先创建项目工程目录

2、然后新建2个文件夹，一个是src文件夹 ，一个是dist文件夹

src:书写ES6的文件夹

dist:利用babel编译成的ES5代码的文件夹

3、新建一个index.html文件，需要在页面引入dist下的index.js文件

4、输入npm init -y,生成一个package.json文件

![](https://upload-images.jianshu.io/upload_images/12693563-94cdf6c0eabf4bf3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5、输入npm install -g babel-cli，全局安装babel-cli命令行，出现下图提示，安装成功

![](https://upload-images.jianshu.io/upload_images/12693563-08711fa992a0dba3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

6、然后安装ES5打包工具，输入npm install --save-dev babel-preset-es2015 babel-cli命令，然后重新打开package.json文件，出现如下两行说明安装成功。
![](https://upload-images.jianshu.io/upload_images/12693563-5b411bc9d72f0fd2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


7、在根目录下创建.babelrc文件，输入json格式的对象

![](https://upload-images.jianshu.io/upload_images/12693563-162709398c06815d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

8、输入babel src/index.js -o dist/index.js即可将ES6语法转换为ES5语法，打开dist文件夹下的index.js文件查看，已经转化成功
![](https://upload-images.jianshu.io/upload_images/12693563-659b09f99ef75d99.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


9、为了避免每次都要输入babel src/index.js -o dist/index.js命令，可以将其放在package.json文件下，scripts就是放命令的地方，可以将其修改为如下命令
![](https://upload-images.jianshu.io/upload_images/12693563-ff6419ce594b5243.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/12693563-10c10b6e2796d50c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


10、输入npm run build命令即可转换成功