vue项目上安装SCSS和开发入门



① 使用vue-cli模板创建新项目：vue init webpack myvue

② 安装sass 依赖包 ，在cmd界面输入：

npm  install sass-loader --save-dev
npm install node-sass --sava-dev

③ 在build文件夹下的webpack.base.conf.js的rules里面添加配置


{
test: /\.scss$/,
loaders: ['style', 'css', 'sass']
}
④ 使用scss时候在所在的style样式标签上添加lang=”scss”即可应用对应的语法，否则报错

⑤ scss使用测试：如下测试修改字体颜色

<style lang="scss">
$color:red;
div {color:$color;}
</style>

报错：TypeError: this.getResolve is not a function

原因：安装的sass-loader的版本为最新8.0.0

解决方法：把项目package.json文件中sass-loader版本改为7.3.1。