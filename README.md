# mui-plus-webview
一个基于mui的网页端模拟webview拓展

模拟触发了plusReady事件

主要利用iframe,对webview进行模拟

以及一些mui.js中使用到的plus方法/属性的模拟

# 适用场景

- 开始是app代码,没时间转换为浏览器端代码的

- 需要在浏览器端查看webview效果的

# 使用方法

在入口页面引入./js/plus.js文件即可

# 注意事项

- 需要引入mui.js,mui.css
    \(js方面是因为使用了mui.extend,mui.type,mui.slice等方法\)
    \(css方面是因为使用了mui的mask等样式\)

- ios的web端使用本库时,会把iframe的html,body,.mui-content的高度设置为100%

- ifrme容器的z-index的基数为500
    \(设置"webview"的zindex其实是设置iframe容器的z-index\)
    \(但是设置样式的配置按照[plus文档](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewStyles)来就好,有相关代码进行转换\)

# 实现功能

- [ ] [webview](http://www.html5plus.org/doc/zh_cn/webview.html)\(动画相关待完成\)
    - 方法：
      - [x] [all](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.all): 获取所有Webview窗口
      - [x] [close](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.close): 关闭Webview窗口
      - [x] [create](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.create): 创建新的Webview窗口
      - [x] [currentWebview](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.currentWebview): 获取当前窗口的WebviewObject对象
      - [ ] [getDisplayWebview](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.getDisplayWebview): 获取屏幕所有可视的Webview窗口
      - [x] [getWebviewById](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.getWebviewById): 查找指定标识的WebviewObject窗口
      - [x] [getLaunchWebview](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.getLaunchWebview): 获取应用首页WebviewObject窗口对象
      - [ ] [getSecondWebview](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.getSecondWebview): 获取应用第二个首页WebviewObject窗口对象
      - [ ] [getTopWebview](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.getTopWebview): 获取应用显示栈顶的WebviewObject窗口对象
      - [x] [hide](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.hide): 隐藏Webview窗口
      - [x] [open](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.open): 创建并打开Webview窗口
      - [ ] [prefetchURL](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.prefetchURL): 预载网络页面
      - [ ] [prefetchURLs](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.prefetchURLs): 预载网络页面（多个地址）
      - [x] [show](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.show): 显示Webview窗口
      - [ ] [startAnimation](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.startAnimation): Webview窗口组合动画
      - [ ] [defaultHardwareAccelerated](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.defaultHardwareAccelerated): 获取Webview默认是否开启硬件加速
  - [ ] WebviewObject
      - 属性：
        - [x] [id](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.id): Webview窗口的标识
      - 方法：
        - [x] [addEventListener](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.addEventListener): 添加事件监听器
        - [x] [append](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.append): 在Webview窗口中添加子窗口
        - [ ] [appendJsFile](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.appendJsFile): 添加Webview窗口预加载js文件
        - [ ] [animate](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.animate): Webview窗口内容动画
        - [x] [back](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.back): 后退到上次加载的页面
        - [x] [beginPullToRefresh](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.beginPullToRefresh): 开始Webview窗口的下拉刷新
        - [x] [canBack](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.canBack): 查询Webview窗口是否可后退
        - [ ] [canForward](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.canForward): 查询Webview窗口是否可前进
        - [ ] [checkRenderedContent](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.checkRenderedContent): 检测Webview窗口是否渲染完成
        - [x] [children](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.children): 获取Webview窗口的所有子Webview窗口
        - [x] [clear](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.clear): 清空原生Webview窗口加载的内容
        - [x] [close](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.close): 关闭Webview窗口
        - [ ] [drag](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.drag): 设置Webview窗口的滑屏操作手势
        - [ ] [draw](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.draw): 截屏绘制
        - [ ] [endPullToRefresh](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.endPullToRefresh): 结束Webview窗口的下拉刷新
        - [x] [evalJS](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.evalJS): 在Webview窗口中执行JS脚本
        - [x] [forward](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.forward): 前进到上次加载的页面
        - [ ] [getFavoriteOptions](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getFavoriteOptions): 获取Webview窗口的收藏参数
        - [ ] [getShareOptions](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getShareOptions): 获取Webview窗口的分享参数
        - [x] [getStyle](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getStyle): 获取Webview窗口的样式
        - [x] [getSubNViews](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getSubNViews): 获取Webview窗口的原生子View控件对象
        - [x] [getTitle](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getTitle): 获取Webview窗口加载HTML页面的标题
        - [ ] [getTitleNView](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getTitleNView): 获取Webview窗口的标题栏控件对象
        - [x] [getURL](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.getURL): 获取Webview窗口加载HTML页面的地址
        - [x] [hide](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.hide): 隐藏Webview窗口
        - [ ] [interceptTouchEvent](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.interceptTouchEvent): 是否拦截Webview窗口的触屏事件
        - [x] [isHardwareAccelerated](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.isHardwareAccelerated): 查询Webview窗口是否开启硬件加速
        - [x] [isVisible](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.isVisible): 查询Webview窗口是否可见
        - [ ] [listenResourceLoading](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.listenResourceLoading): 监听页面开始加载资源
        - [ ] [loadData](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.loadData): 加载新HTML数据
        - [ ] [loadURL](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.loadURL): 加载新URL页面
        - [ ] [nativeInstanceObject](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.nativeInstanceObject): 获取Webview窗口对象的原生（Native.JS）实例对象
        - [x] [opened](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.opened): 获取在当前Webview窗口中创建的所有窗口
        - [x] [opener](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.opener): 获取当前Webview窗口的创建者
        - [ ] [overrideResourceRequest](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.overrideResourceRequest): 拦截Webview窗口的资源加载
        - [ ] [overrideUrlLoading](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.overrideUrlLoading): 拦截Webview窗口的URL请求
        - [x] [parent](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.parent): 获取当前Webview窗口的父窗口
        - [x] [reload](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.reload): 重新加载Webview窗口显示的HTML页面
        - [ ] [resetBounce](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.resetBounce): 重置Webview窗口的回弹位置
        - [ ] [restore](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.restore): 恢复Webview控件显示内容
        - [ ] [remove](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.remove): 移除子Webview窗口
        - [x] [removeEventListener](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.removeEventListener): 移除Webview窗口事件监听器
        - [x] [removeFromParent](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.removeFromParent): 从父窗口中移除
        - [ ] [setBounce](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setBounce): 设置Webview窗口的回弹效果
        - [ ] [setBlockNetworkImage](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setBlockNetworkImage): 设置Webview窗口是否阻塞加载页面中使用的网络图片
        - [ ] [setContentVisible](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setContentVisible): 设置HTML内容是否可见
        - [ ] [setFavoriteOptions](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setFavoriteOptions): 设置Webview窗口的收藏参数
        - [ ] [setPullToRefresh](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setPullToRefresh): 设置Webview窗口的下拉刷新效果
        - [ ] [setRenderedEventOptions](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setRenderedEventOptions): 设置Webview窗口rendered事件参数
        - [x] [setStyle](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setStyle): 设置Webview窗口的样式
        - [ ] [setShareOptions](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setShareOptions): 设置Webview窗口的分享参数
        - [ ] [setJsFile](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setJsFile): 设置预加载的JS文件
        - [ ] [setCssFile](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setCssFile): 设置预加载的CSS文件
        - [ ] [setCssText](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setCssText): 设置预加载的CSS内容
        - [x] [setVisible](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setVisible): 设置Webview窗口是否可见
        - [ ] [setFixBottom](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.setFixBottom): 设置Webview窗口底部修复区域高度
        - [x] [show](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.show): 显示Webview窗口
        - [ ] [showBehind](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.showBehind): 在指定Webview窗口后显示
        - [ ] [stop](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.stop): 停止加载HTML页面内容
        - [ ] [updateSubNViews](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.updateSubNViews): 更新Webview窗口的原生子View控件对象
      - 事件：
        - [ ] [onclose](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.onclose): Webview窗口关闭事件
        - [ ] [onerror](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.onerror): Webview窗口错误事件
        - [ ] [onloaded](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.onloaded): Webview窗口页面加载完成事件
        - [ ] [onloading](http://www.html5plus.org/doc/zh_cn/webview.html#plus.webview.WebviewObject.onloading): Webview窗口页面开始加载事件

## 其他plus代码实现

> checked状态表示调用有效果

> 否则表示能调用,但无效果(空操作)

> 对未列出的属性/方法进行调用将会返回undefined

- [ ] [device](http://www.html5plus.org/doc/zh_cn/device.html)
  - 方法：
  - [x] [device](http://www.html5plus.org/doc/zh_cn/device.html#plus.device.dial): 拨打电话

- [ ] [key](http://www.html5plus.org/doc/zh_cn/key.html)
  - 方法：
  - [ ] [addEventListener](http://www.html5plus.org/doc/zh_cn/key.html#plus.key.addEventListener): 添加按键事件监听器
  - [ ] [removeEventListener](http://www.html5plus.org/doc/zh_cn/key.html#plus.key.removeEventListener): 移除按键事件监听器

- [ ] [runtime](http://www.html5plus.org/doc/zh_cn/runtime.html)
  - 属性：
  - [x] [appid](http://www.html5plus.org/doc/zh_cn/runtime.html#plus.runtime.appid): 当前应用的APPID
  - 方法：
  - [x] [quit](http://www.html5plus.org/doc/zh_cn/runtime.html#plus.runtime.quit): 退出客户端程序\( __表现为打开个空页面__ \)

- [ ] [nativeUI](http://www.html5plus.org/doc/zh_cn/nativeUI.html)
  - 方法：
  - [x] [closeWaiting](http://www.html5plus.org/doc/zh_cn/nativeui.html#plus.nativeUI.closeWaiting): 关闭系统等待对话框
  - [x] [showWaiting](http://www.html5plus.org/doc/zh_cn/nativeui.html#plus.nativeUI.showWaiting): 显示系统等待对话框

- [ ] [navigator](http://www.html5plus.org/doc/zh_cn/navigator.html)
  - 方法：
  - [ ] [closeSplashscreen](http://www.html5plus.org/doc/zh_cn/navigator.html#plus.navigator.closeSplashscreen): 关闭应用启动界面

- [ ] [net](http://www.html5plus.org/doc/zh_cn/net.html)
  - 构造：
  - [x] [XMLHttpRequest()](http://www.html5plus.org/doc/zh_cn/xhr.html#plus.net.XMLHttpRequest.XMLHttpRequest()): 创建一个XMLHttpRequest 对象，对象创建时不触发任何时间和网络请求，需和open，send方法配合使用。

## 添加的mui方法

- mui.prop_attr

  ``` javascript
  /**
   * prop_attr
   * @param {attrs/props/name} ObjectOrString 属性键值对or属性名
   * @param {target/value} NodeOrString 目标对象or期望设置的值
   * @return {value} 传入name时返回对应的属性值
   */
  ```
  
  > 设置或返回被选元素的"自带/自定义"属性值。

  > 可参考jQuery的[attr](http://www.runoob.com/jquery/html-attr.html)/[prop](http://www.runoob.com/jquery/html-prop.html)文档