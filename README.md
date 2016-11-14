> 一个简单的sass打包示例，旨在演示如何在项目中将使用的sass(CSS预处理器)文件通过webpack的方式打包到一个js文件中供项目使用

# 1. npm安装依赖包
需要安装的npm包如下：
* webpack --打包工具
* css-loader --read css file
* style-loader --将css style插入html页面
* sass-loader --read sass file(.scss)
* node-sass --sass-loader依赖node-sass    
> npm install webpack css-loader style-loader sass-loader node-sass --save-dev   


> 注意：
node-sass安装可能会出现如下错误：
Start downloading binary at https://github.com/sass/node-sass/releases/download/ v3.10.0/win32-ia32-46_binding.node
Cannot download "https://github.com/sass/node-sass/releases/download/v3.10.0/win
32-ia32-46_binding.node":
这是因为amazon服务在国内不稳定导致的，我尝试了不少方法一直没有解决，
最终解决的方法记录如下：
1. git clone https://github.com/sass/node-sass.git下载node-sass项目文件
到本地/node_modules/文件夹。
2. 翻墙或者多次尝试在浏览器下直接输入如下地址，下载该文件，是可以下载成功的。 https://github.com/sass/node-sass/releases/download/v3.10.0/win32-ia32-46_binding.node
3. 重命名文件为binding.node,copy至node-sass\vendor\win32-ia32-46目录，不存在
win32-ia32-46目录则自行创建(本人使用的系统为win7 32位系统，需根据系统情况变化)。
4. cd到nodes-sass根目录，执行npm install则可以安装成功。

# 2. 由于示例非常简单，直接看源码即可，terminal下执行webpack命令会生成bundle.js，打开index.html文件后可以看到页面背景颜色被改变，说明工作正常。

# 3. cpm在国内下载包是非常慢的，起始可以使用cnpm来代替npm命令（该步骤是步骤1的替代选项，国内推荐）
> cnpm是阿里团队推出的工具，通过淘宝镜像进行安装，速度非常快
1. 首先需要安装cnpm：
` $ npm install -g cnpm --registry=https://registry.npm.taobao.org

2. 通过cnpm安装的依赖包：
* webpack --打包工具
* css-loader --read css file
* style-loader --将css style插入html页面
* sass-loader --read sass file(.scss)
* node-sass --sass-loader依赖node-sass    
` cnpm install webpack css-loader style-loader sass-loader node-sass --save-dev
> 通过cnpm安装node-sass不会出现错误
