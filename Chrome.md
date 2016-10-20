## *Chrome的调试*
- **Ctrl+shift+C、F12或者右键开发者工具-->打开调试器**
- **调试器的黑色主题**
 - 在chrome商店下载安装主题：[安装地址](https://chrome.google.com/websto … gdgfoefmpeafkjhegbo)
 - chrome地址栏输入：`chrome://flags` 找到`experiments`关键字：启用开发者工具实验。
 - 打开调试器（F12），点击设置（setting啥的）：在`Experiments`中，选中`Allow custom UI themes`。
 - 然后重启，打开调试器，你会发现~炫酷的黑色主题
 
 -------------------------------------------------------
 
- **有关调试的技巧（自己整理了一下）、来自原创[网站](http://seejs.me/2016/03/27/jsdebugger/)**
 - 内置于Window对象中的alert方法(被玩坏了的) 
 
     <img src=picture/alert.gif width=400 height=200 />
  
 - alert调试方式弹出的调试信息，  弹窗会遮挡部分页面内容。另一方面，程序逻辑中添加类似”alert(xxxxx)”这样的语句，会阻碍页面的继续渲染。  现在出现”console.log(xxxx)”的形式，在控制台打印调试信息，而不直接影响页面显示。以IE为例，它看起来像这样：
 
      <img src=picture/console.gif width=400 height=200 />

 - 好吧，再见丑陋的alert弹出框。而以Chrome浏览器为首的后起之秀，为Console扩展了更丰富的功能：

       <img src=picture/console.table_.gif width=400 height=200 />

 - 还有一些其的打印功能
 
        <img src=picture/consolec.gif width=400 height=200 />
        
- **断点调试**
 - **附上调试代码(代码很简单，就是定义一个函数，传入两个数，分别加上一个乱七八糟的随机整数后，再返回两个数的总和。以Chrome开发者工具为例，我们来看一下JS断点调试的基本方法。)：**
 
 ```javascript
 <script>
    (function () {
        function sum(a, b) {
            console.log('传入实参: a=' + a + ', b=' + b);
            var c = Math.random() * 10;
            c = parseInt(c);
            console.log('被加的随机数为：' + c);
            a += c;
            b += 2 * c;
            console.log('变化后的a、b=' + a + ', b=' + b);
            return a + b;
        }

        console.log(sum(10, 20));
    })();
</script>
 ```
 

 - 设置断点的作用（查看相应变量的变化`图中粉红色区域`）
  
     <img src=picture/breakpoint-sum2.gif width=500 height=300 />
     

  - 打开Sources面板后其实会在界面中看到如下内容，我们跟着鼠标轨迹逐一看看都是什么意思：
     
     <img src=picture/breakpoint-sum4.gif width=400 height=70 />
     
     从左到右，各个图标表示的功能分别为：
     
     
     - [x] Pause/Resume script execution：暂停/恢复脚本执行（程序执行到下一断点停止）。
     
     - [x] Step over next function call：执行到下一步的函数调用（跳到下一行）。
     
     - [x] Step into next function call：进入当前函数。
     
     - [x] Step out of current function：跳出当前执行函数。
     
     - [x] Deactive/Active all breakpoints：关闭/开启所有断点（不会取消）。
     
     - [x] Pause on exceptions：异常情况自动断点设置。


  - 到此，断点调试的功能键介绍得差不多了，接下来我们就可以一行一行去看我们的程序代码，查看每一行执行完毕之后，我们各个变量的变化情况了，如下图所示：

     <img src=picture/breakpoint-sum3.gif width=500 height=300 />
     
      **这里要强调一下，调试过程，先点击右上角的停止按钮，如果还调试不行，就在  左边页面刷新一下，然后如下图：在设置的两个断点间按 F10 便会不断进行下一步**
  
     
     <img src=picture/jugelizi.png width=500 height=300 />
     
   
  - 其余几个功能键，稍微改动一下测试代码，用一张gif图来演示他们的使用方法：
   
      
      <img src=picture/breakpoint-sum5.gif width=500 height=300 />
      

  - DOM断点调试当节点内部子节点变化时断点（Break on subtree modifications）
  
 
        <img src=picture/subtree.gif width=500 height=300 />
        
  
  - Event Listener Breakpoints事件监听器断点，即根据事件名称进行断点设置。当事件被触发时，断点到事件绑定的位置。事件监听器断点，列出了所有页面及脚本事件，包括：鼠标、键盘、动画、定时器、XHR等等。极大的降低了事件方面业务逻辑的调试难度。演示实例演示了当click事件被触发时和当setTimeout被设置时的断点效果。实例显示，当选中click事件断点之后，两个按钮的被点击时都触发了断点，而当setTimeout被设置时，“Set Timer”断点被触发。
 
      
      <img src=picture/subtree.gif width=500 height=300 />



----------------------------------------------------------------

##console的相关方法（整理完都是泪）

 - console.log() 接收不定参数，参数间用逗号分隔，最终会输出会将它们以空白字符连接。

 ``` console.log('hi','hello')  //hi hello```


 - 控制台（表格形式输出）：
 
``` var data = [{'品名': '杜雷斯', '数量': 4}, {'品名': '冈本', '数量': 3}];console.table(data); ```

 - 控制台（条件判断输出）：
 
```console.assert(3>2,'不满足条件')  //undefined```

 - 控制台（程序运行时间）：

```console.time('ddd') var dd = function ddd() {return 1+3;}(); dd; console.timeEnd('ddd') //ddd:0.032ms```

```console.time('ddd');
(function dd() {return 1+3;})();
console.timeEnd('ddd');  
//ddd: 0.022ms```


 - 如果不用内置console.time的话：
 
```var start=new Date().getTime();

var array= new Array(1000000);

for (var i = array.length - 1; i >= 0; i--) {

    array[i] = new Object();
    
};

console.log(new Date().getTime()-start);
//236```

 - console.log(Date())
 
```//Sun Oct 16 2016 22:21:36 GMT+0800 (中国标准时间)```


 - shift+Enter可以使控制台换行

 - 控制台（返回属性名组成的数组和属性值的数组）
 
```var tboy={name:'wayou',gender:'unknown',hobby:'opposite to the gender'};
keys(tboy);
//["name", "gender", "hobby"]
values(tboy);
//["wayou", "unknown", "opposite to the gender"]```


 - 格式化打印{ }
  - Chrome的开发者工具有一段嵌入的美化代码，它可以帮你返回一段最小化的且格式易读的代码。这个漂亮的印刷按钮在你正确打开文件之后的Sources标签下的左下角。


###最后扯两句，这chrome.md文件 整理的有点苦逼，不想再commit更新了！！！喜欢的话右上角star一下咯
  








