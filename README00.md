
##console的相关方法（整理完都是泪）

 - console.log() 接收不定参数，参数间用逗号分隔，最终会输出会将它们以空白字符连接。

 ``` console.log('hi','hello')  //hi hello```


 - 控制台（表格形式输出）：
 
``` var data = [{'品名': '杜雷斯', '数量': 4}, {'品名': '冈本', '数量': 3}];console.table(data); ```

 - 控制台（条件判断输出）：
 
```console.assert(3>2,'不满足条件')  //undefined```

 - 控制台（程序运行时间）：

``` console.time('ddd') var dd = function ddd() {return 1+3;}(); dd; console.timeEnd('ddd') //ddd:0.032ms```

``` console.time('ddd');
(function dd() {return 1+3;})();
console.timeEnd('ddd');//ddd: 0.022ms ```
 
 
 - 如果不用内置console.time的话：
 ```var start=new Date().getTime();var array= new Array(1000000);for (var i = array.length - 1; i >= 0; i--) { array[i] = new Object();};console.log(new Date().getTime()-start);//236```


 - console.log(Date()) 
 ```//Sun Oct 16 2016 22:21:36 GMT+0800 (中国标准时间)
 ```


 - shift+Enter可以使控制台换行

 - 控制台（返回属性名组成的数组和属性值的数组）
 
 ```var tboy={name:'wayou',gender:'unknown',hobby:'opposite to the gender'};keys(tboy);//["name", "gender","hobby"]values(tboy);//["wayou", "unknown", "opposite to the gender"]```


 - 格式化打印{ }
  - Chrome的开发者工具有一段嵌入的美化代码，它可以帮你返回一段最小化的且格式易读的代码。这个漂亮的印刷按钮在你正确打开文件之后的Sources标签下的左下角。


###最后扯两句，这chrome.md文件 整理的有点苦逼，不想再commit更新了！！！喜欢的话右上角star一下咯
  