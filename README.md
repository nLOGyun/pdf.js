# pdf.js

通过webview与h5页面交互实现数据互通。详见/fg-transaction-package/pages/fundPurchase/webview/webPage.js 。如果webview接收到了H5页面发送的already字段，则通过路由栈，去触发上一级页面的《我已阅读》事件，如果在页面unload时还未收到already，则将页面再次回退。
H5页面用法：
基金产品资料概要  点击按钮  发送通知
wx.miniProgram.postMessage({
     	data: {
       	type: 'fundClick',
       	already: true
     	}
 })
