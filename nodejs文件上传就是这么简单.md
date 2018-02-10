---
title: nodejs文件上传就是这么简单
tags:
  - 文件上传
categories:
  - nodejs
---

#### 安装如下包：

`npm install multer`

package versions:

`"multer": "^1.1.0",`
<!-- more -->
#### 使用方法：

```
/**
 *
 * @Description 系统服务
 * @Author Amor
 * @Created 2016/04/27 15:27
 * 技术只是解决问题的选择,而不是解决问题的根本...
 * 我是Amor,为发骚而生!
 *
 */
var express = require('express');
var router = express.Router();
var upload = require('./fileupload');

//文件上传服务
router.post('/upload', upload.single('avatar'), function (req, res, next) {
    if (req.file) {
        res.send('文件上传成功')
        console.log(req.file);
        console.log(req.body);
    }
});

module.exports = router;
```
#### config.js
```
/**
 *
 * @Description 系统配置
 * @Author Amor
 * @Created 2016/04/26 11:48
 * 技术只是解决问题的选择,而不是解决问题的根本...
 * 我是Amor,为发骚而生!
 *
 */

module.exports = {
    upload: {
        path: process.cwd() + '/uploads'
    }
}
```
#### fileuploads.js
```
/**
 *
 * @Description 文件上传配置
 * @Author Amor
 * @Created 2016/04/27 17:50
 * 技术只是解决问题的选择,而不是解决问题的根本...
 * 我是Amor,为发骚而生!
 *
 */
var multer = require('multer');
var config = require('./config')

var storage = multer.diskStorage({
    //设置上传文件路径,以后可以扩展成上传至七牛,文件服务器等等
    //Note:如果你传递的是一个函数，你负责创建文件夹，如果你传递的是一个字符串，multer会自动创建
    destination: config.upload.path,
    //TODO:文件区分目录存放
    //重命名
filename: function (req, file, cb) {
        var fileFormat =(file.originalname).split(".");
        cb(null, file.fieldname + "." + fileFormat[fileFormat.length - 1]);
    }
});

//添加配置文件到muler对象。
var upload = multer({
    storage: storage,
    //其他设置请参考multer的limits
    //limits:{}
});
//导出对象
module.exports = upload;
```

#### form:
```
<form id='editfile' method='post' action='/system/upload' enctype='multipart/form-data'>
    <input name="text" type="text"/>
    选择图片：<input name="avatar" id='upfile' type='file'/>
    <input type='submit' value='提交'/>
</form>
```
目前只是实现基本上传功能，还有许多待处理，比如错误处理、上传大小限制，图片压缩等等，如果需要，请自行扩展。

#### 代码地址：
<div class="github-card" data-github="amor520/nodejs-file-upload-multer" data-width="400" data-height="297" data-theme="medium"></div>
<script src="//cdn.jsdelivr.net/github-cards/latest/widget.js"></script>

转载请注明原地址，谢谢！
