## *Chrome的调试*
- **Ctrl+shift+C、F12或者右键开发者工具-->打开调试器**
- **调试器的黑色主题**
 - 在chrome商店下载安装主题：[安装地址](https://chrome.google.com/websto … gdgfoefmpeafkjhegbo)
 - chrome地址栏输入：`chrome://flags` 找到`experiments`关键字：启用开发者工具实验。
 - 打开调试器（F12），点击设置（setting啥的）：在`Experiments`中，选中`Allow custom UI themes`。
 - 然后重启，打开调试器，你会发现~~炫酷的黑色主题
- **断点调试**
 - “逐过程执行”按钮，和“逐语句执行”按钮不同（单、双击转换）
“逐过程执行”按钮常用在一个方法调用多个js文件时，涉及到的js代码比较长，则会使用到这个按钮。
最重要的是：重新加载，
<iframe height=500 width=500 src="breakpoint-sum.gif.gif"> 
