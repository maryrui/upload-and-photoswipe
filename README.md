# upload-and-photoswipe
lifeTime
效果展示
![image](https://github.com/maryrui/upload-and-photoswipe/blob/master/img/one.png)
![image](https://github.com/maryrui/upload-and-photoswipe/blob/master/img/one.png)
点击图片幻灯片播放，欢动切换，开始逻辑准备用swipe 插件完成，但是给swipe父元素定位后，出现的滑动问题（放弃方案）。
photoswipe使用过程中发现问题:
1.关于自定义按钮
    完成页面的删除按钮，查找官方文档还有github的issues 作者基本上没有回答，所以自定图标，删除按钮，定位之后调用photoswipe 关闭方法（close）.
2.关于传参图片高度宽度只能固定数字
    解决就是重新定义css样式，覆盖样式（同事提醒）
3.构造函数有很多方法，比如获取打开照片的getCurrentIndex,close

关于配置的参数如图：
![image](https://github.com/maryrui/upload-and-photoswipe/blob/master/img/three.png)

关于上传预览问题
方法1：window.createObjectURL（刚开始用这个方法，问题出现在，）
      创建一个新的对象URL,该对象URL可以代表某一个指定的File对象或Blob对象.
      blob参数是一个File对象或者Blob对象.
      objectURL是生成的对象URL.通过这个URL,可以获取到所指定文件的完整内容.
      在每次调用createObjectURL()方 法的时候,都会创建一个新的对象URL,即使参数中的这个对象已经有了自己的对象URL.在你不需要这些对象URL的时候,你应该通过       调用 window.URL.revokeObjectURL()方法来释放它们所占用的内容.虽然即使你不主动释放它们,浏览 器也会在当前文档被卸载的时候替你释放,不过,考虑到更好        的性能和更少的内存占用,你应该在安全的时候主动施放它们.
 方法2：使用FileReader 对象允许Web应用程序异步读取存储在用户计算机上的文件（或原始数据缓冲区）的内容，使用 File 或 Blob 对象指定要读取的文件或数据。
      其中File对象可以是来自用户在一个<input>元素上选择文件后返回的FileList对象,也可以来自拖放操作生成的 DataTransfer对象,还可以是来自在一个         HTMLCanvasElement上执行mozGetAsFile()方法后返回结果.
      https://developer.mozilla.org/zh-CN/docs/Web/API/FileReader

手机效果预览
  ![image](https://github.com/maryrui/upload-and-photoswipe/blob/master/img/phone_preview.png)
