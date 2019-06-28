### webpack 究竟是什么
    webpack是一个模块打包工具 webpack is a moudule bundler
### webpack打包流程
1. 在使用webpack打包的时候由于webpack并不知道使用者的意图所以它会根据你给它提供的js文件按照默认配置来打包 根据工程的特点和复杂程度 所以我们应当根据不同工程编写不同的配置文件 当你给它提供自定义的webpack.config.js的时候，它就会根据配置文件进行打包
### 安装webpack
- 全局安装
  - npm install webpack webpack-cli -g //`webpack-cli的作用是得以在命令行中使用npm下的各种命令`
  - npm webpack -index.js //根据默认配置来打包index.js到dist/main.js
- 项目内安装
  - npm install webpack webpack-cli -D//`-D == --save-dev`
  - npx webpack -index.js //同上 如果文件夹下有webpack.config.js index.js即可省略 

### webpack打包输出内容
- hash
- version
- time
- built at
- assset 输出的js文件
- size
- chunks 打包出的所有文件的id值
- chunks names 打包出的文件名
- Entrypoint main = [index] 入口文件的打包顺序
### 模块引入语法
> webpack documentation api modules
1. ES Moudule
   1. export default ...
   2. import ... from ...
2. CommonJs
   1. module.exports = ...
   2. require()
3. CMD
4. ADM
### 常用命令的作用
    npm init //初始化一个npmpackage配置文件 创建一个符合node规范的项目
    npx webpack --config [配置文件名]

### loader
> loader是一个打包的方案

> loader执行顺序 从上到下 从右到左

- file-loader
- url-loader
- style-loader 得到css-loader合并之后的内容之后将之挂载到head部分
- css-loader 分析css文件之间的关系 合并成一段css
- sass-loader
- postcss-loader 需要创建postcss.config.js并引入autoprefixer
### webpack.config.js
```javascript
const path = require('path');

module.exports = {
    //默认mode:'production'
    mode: 'development',
    entry: {
        main: './src/index.js'
    },//简写 entry:'./src/index.js',
    module: {//模块打包配置
        rules: [{
            test: /\.jpg$/,
            use: {
                loader: 'file-loader',
                options:{
                    name:'[name].[ext]',//placeholder：占位符
                    outputPath:'images/'
                }
            } 
        }]
    },
    output: {
        filename: 'main.js',//输出文件名
        path: path.resolve(__dirname, 'dist')//默认配置即为如此
    }
}
```
### package.json
```json
{
    "name": "webpack-demo",
    //项目名
    "version": "1.0.0",
    //项目版本
    "description": "",
    //项目描述
    "main":"index.js",
    //暴露给其他程序的main文件 按需删留
    "private": true,
    //是否私有
    "scripts": {
        "serve":"webpack"
        //npm run serve ==npm webpack
    },
    //自定义脚本命令 优先从本项目的目录中寻找webpack
    "author": "Youin",
    //作者
    "license": "ISC",
    //协议
    "devDependencies": {
    "webpack": "^4.34.0",
    "webpack-cli": "^3.3.4"
    }

}
```