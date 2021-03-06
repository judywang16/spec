# 组件化公共资源库准入规范

## 提交说明

公共库接受提交以zip文件打包的任意代码、图片内容，zip包内的必须有一个output文件夹存放待上传的公共库压缩文件或图片。审核通过完成上线后，可通过NA内本地路径和平台CDN访问。
~~~
demo.zip
├── output/                    # 上传内容
│   ├── ...                    # 需上传的公共库压缩CSS/JS文件或图片
│
│   ├── ...                    # 开发源码
│       └── ...
~~~



## 命名规范

0. 路径的任意位置不允许出现空格。
1. 公共资源文件名称需体现文件内容。
2. JS相关公共资源需要压缩，命名格式：xxx_1.0.0.min.js
3. Image相关公共资源需要注明尺寸，倍率，格式：xxx_40x40@2x.png
4. CSS相关公共资源需要压缩，命名格式：xxx.min.css
 
## 上传第三方库文件注意事项

1. 需上传开源库资源说明文档地址。
2. 需要注明版本。
3. 若有修改，需要注明修改处及修改原因。
4. 引用类似zepto这种可以选择模块的第三方库时，需注明引用模块。
5. 同一个库文件同版本，不可多次上传。
 
## 非第三方库文件注意事项

1. 开发代码必须通过FECS检查。
2. 不可随意放置变量到全局对象。
3. 不可修改共有的原型链，比如：在Object, Array等原生对象的原型链上添加方法。
4. 开发对外开放接口需要有完善的说明文档。需展示API列表、使用说明，最佳实践和例子，更新日志。
5. 暴露API接口设计需简单易用，便于扩展。接口传参需考虑扩展性。
6. 完善的类型检查，异常处理，边界值判断。
7. 库的生命周期定义。
8. 使用ES5导出对象不可以用defined属性作为字段名，不可以使用exports.default导出。
9. 开发语法需统一，ES5和ES6不可混用。
10. 合理使用注释。
