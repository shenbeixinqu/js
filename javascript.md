# javascript

## js基础

### 注释

单行注释  //           ctrl +  /

多行注释  /*  */      alt+shift+/

### 输入输出

<script>
        // 这是一个输入框
        prompt('请输入您的年龄');
        // alert 弹出警示框 输出的 展示给用户的
        alert('计算的结果是');
        // console 控制台输出 给程序员测试用的  
        console.log('我是程序员能看到的');
    </script>

### 变量赋值

  <script>
        // 1. 声明了一个age 的变量 
        var age;
        // 2. 赋值  把值存入这个变量中
        age = 18;
        // 3. 输出结果 
        console.log(age);
        // 4. 变量的初始化 
        var myname = 'pink老师';
        console.log(myname);
    </script>

### 数据类型转换

```js
 console.log(parseInt('3.14')); // 3 取整
        console.log(parseInt('3.94')); // 3 取整
        console.log(parseInt('120px')); // 120 会去到这个px单位
        console.log(parseInt('rem120px')); // NaN
        // 2. parseFloat(变量) 可以把 字符型的转换为数字型 得到是小数 浮点数
        console.log(parseFloat('3.14')); // 3.14
        console.log(parseFloat('120px')); // 120 会去掉这个px单位
        console.log(parseFloat('rem120px')); // NaN
```

### switch语句

```js
 <script>
        var fruit = prompt("请输入水果")
        switch(fruit){
            case '苹果':
            alert("3.5/斤");
            break;
            case '菠萝':
            alert("20/斤");
            break;
            default:
            alert("没有此水果")
        }
</script>
```

### 循环do-while

```javascript
  // 1.do while 循环 语法结构
        do {
            // 循环体
        } while (条件表达式)
        // 2.  执行思路 跟while不同的地方在于 do while 先执行一次循环体 在判断条件 如果条件表达式结果为真，则继续执行循环体，否则退出循环
        // 3. 代码验证
        var i = 1;
        do {
            console.log('how are you?');
            i++;
        } while (i <= 100)
        // 4. 我们的do while 循环体至少执行一次
```

### 遍历数组

```js
var arr = ['aaa','bbb','ccc']
        for (var i = 0;i < 3;i++){
            console.log(arr[i])
```

因为我们的数组索引号从0开始 ，所以 i 必须从 0开始  i < 3

### 获取数组的长度

```javascript
 var arr = ['aaa','bbb','ccc']
        for (var i = 0;i < arr.length;i++){
            console.log(arr[i])
        }
```

arr.length

### 函数的形参和实参

如果实参的个数小于形参的个数，多余的形参定义为undefined,最终的结果为NAN

### 求数组的最大值

```javascript
<script>
        function arrMax(arr){
            var max = arr[0];
            for (var i = 1;i<=arr.length;i++){
                if (arr[i]>max){
                    max = arr[i];
                }
            } return max;
        }
        var re = arrMax([1,23,323,451,23]);
        console.log(re);
</script>
```

### arguments

arguments 的使用  只有函数才有 arguments对象  而且是每个函数都内置好了这个arguments

arguments 伪数组

// 伪数组 并不是真正意义上的数组
        // 1. 具有数组的 length 属性
        // 2. 按照索引的方式进行存储的
        // 3. 它没有真正数组的一些方法 pop()  push() 等等

```javascript
  function fn() {
            // console.log(arguments); // 里面存储了所有传递过来的实参  arguments = [1,2,3]
            // console.log(arguments.length);
            // console.log(arguments[2]);
            // 我们可以按照数组的方式遍历arguments
            for (var i = 0; i < arguments.length; i++) {
                console.log(arguments[i]);

            }
        }
        fn(1, 2, 3);
        fn(1, 2, 3, 4, 5);
```

### 变量的作用域

// 变量的作用域： 根据作用域的不同我们变量分为全局变量和局部变量
// 1. 全局变量： 在全局作用域下的变量 在全局下都可以使用
// 注意 如果在函数内部 没有声明直接赋值的变量也属于全局变量

// 2. 局部变量   在局部作用域下的变量   后者在函数内部的变量就是 局部变量
 // 注意： 函数的形参也可以看做是局部变量

// 3. 从执行效率来看全局变量和局部变量
        // (1) 全局变量只有浏览器关闭的时候才会销毁，比较占内存资源
        // (2) 局部变量 当我们程序执行完毕就会销毁， 比较节约内存资源

### 对象

对象的属性和方法的调用和python一致

new方法创建对象

```javascript
 <script>
        var obj = new Object();
        obj.name = "ass";
        obj.age = 13
        obj.say = function(){
            console.log("sayhi");
            
        }
        console.log(obj.name);
        console.log(obj["age"]);
        obj.say()
        
    </script>
```

构造函数创建对象

```javascript
 <script>
        function Star(name,age,sex){
            this.name = name,
            this.age = age,
            this.sex = sex
        }
        var ldh = new Star("liudehua",23,"男")
        console.log(ldh.name);
        console.log(ldh.sex)
        
    </script>
```

        // 1. 构造函数名字首字母要大写
        // 2. 我们构造函数不需要return 就可以返回结果
        // 3. 我们调用构造函数 必须使用 new
        // 4. 我们只要new Star() 调用函数就创建一个对象 ldh  {}
        // 5. 我们的属性和方法前面必须添加 this
### new关键字的执行过程

- 在内存中创建一个空对象
- 让this指向这个新的对象
- 执行构造函数里面的代码,给这个新对象添加属性和方法
- 返回这个新对象

### 遍历对象属性

```javascript
<script>
        var obj = {
            name : "asd",
            age : 15
        }
        // console.log(obj.name);
        // console.log(obj["age"]);
        for (var k in obj){
            console.log(k); // 变量
            console.log(obj[k]); //属性值
        }
</script>
```

### 内置对象

js中的对象分为三种：自定义对象，内置对象，浏览器对象

### Math对象

```javascript
绝对值方法
console.log(Math.abs(1)); // 1
向下取整
console.log(Math.floor(1.1)); // 1
console.log(Math.floor(1.9)); // 1
向上取整
console.log(Math.ceil(1.1)); // 2
console.log(Math.ceil(1.9)); // 2
四舍五入  其他数  遇见.5 向较大的数取值
console.log(Math.round(1.5)); // 2
console.log(Math.round(-1.5)); // 这个结果是 -1
返回两个数之间的随机整数
Math.floor(Math.random()*(max-min+1))+min
```

## WEBAPI

### 获取元素

####　通过id

```javascript
<script>
        var tmper = document.getElementById("time")
        console.log(tmper);
		# 打印返回的元素对象，更好的获得属性和方法
        console.dir(tmper)
</script>
```

#### 通过name

```javascript
// 5. element.getElementsByTagName('标签名'); 父元素必须是指定的单个元素
// var ol = document.getElementsByTagName('ol'); // [ol]
// console.log(ol[0].getElementsByTagName('li'));
var ol = document.getElementById('ol');
console.log(ol.getElementsByTagName('li'));
```



#### h5 新增

```javascript
# 根据类名
var boxs = document.getElementsByClassName('box');
# 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav
 var firstBox = document.querySelector('.box');
# 返回指定选择器的所有元素对象集合
var allBox = document.querySelectorAll('.box');
```

#### 获取特殊元素

```javascript
# 获取body
var bodyEle = document.body;
# 获取html元素
var htmlEle = document.documentElement;

```

### 事件三要素

```javascript
# 事件是有三部分组成  事件源  事件类型  事件处理程序   我们也称为事件三要素
# //(1) 事件源 事件被触发的对象   谁  按钮
 var btn = document.getElementById('btn');
//(2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
//(3) 事件处理程序  通过一个函数赋值的方式 完成
btn.onclick = function() {
    alert('点秋香');
}

```

### 操作元素改变内容

```javascript
// 当我们点击了按钮，  div里面的文字会发生变化
// 1. 获取元素 
var btn = document.querySelector('button');
var door = document.querySelector('div');
// 2.注册事件
btn.onclick = function() {
// div.innerText = '2019-6-6';
door.innerHTML = getDate();
}

```

### innerText和innerHTML的区别

```javascript
// 1. innerText 不识别html标签 非标准  去除空格和换行
// 2. innerHTML 识别html标签 标准  不去除空格和换行
```

### 修改元素的属性

```javascript
 // 1. 获取元素
var ldh = document.getElementById('ldh');
var zxy = document.getElementById('zxy');
var img = document.querySelector('img');
// 2. 注册事件  处理程序
zxy.onclick = function() {
    img.src = 'images/zxy.jpg';
    img.title = '张学友思密达';
}
ldh.onclick = function() {
    img.src = 'images/ldh.jpg';
    img.title = '刘德华';
}
```

### 操作元素表单属性

```javascript
// 1. 获取元素
var btn = document.querySelector('button');
var input = document.querySelector('input');
// 2. 注册事件 处理程序
btn.onclick = function() {
    // input.innerHTML = '点击了';  这个是 普通盒子 比如 div 标签里面的内容
    // 表单里面的值 文字内容是通过 value 来修改的
    input.value = '被点击了';
    // 如果想要某个表单被禁用 不能再点击 disabled  我们想要这个按钮 button禁用
    // btn.disabled = true;
    this.disabled = true;
    // this 指向的是事件函数的调用者 btn
        }
```

### 案例：京东隐藏显示密码

```javascript
 // 1. 获取元素
var eye = document.getElementById('eye');
var pwd = document.getElementById('pwd');
// 2. 注册事件 处理程序
var flag = 0;
eye.onclick = function() {
    // 点击一次之后， flag 一定要变化
    if (flag == 0) {
        pwd.type = 'text';
        eye.src = 'images/open.png';
        flag = 1; // 赋值操作
    } else {
        pwd.type = 'password';
        eye.src = 'images/close.png';
        flag = 0;
    }

}
```

### 修改样式属性

```javascript
// 1. 获取元素
var div = document.querySelector('div');
// 2. 注册事件 处理程序
div.onclick = function() {
    // div.style里面的属性 采取驼峰命名法 
    this.style.backgroundColor = 'purple';
    this.style.width = '250px';
}
```

### 排他思想

```javascript
   <script>
        var btns = document.getElementsByTagName("button");
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                // (1) 我们先把所有的按钮背景颜色去掉  干掉所有人
                for (var i = 0; i < btns.length; i++) {
                    btns[i].style.backgroundColor = '';
                }
                // (2) 然后才让当前的元素背景颜色为pink 留下我自己
                this.style.backgroundColor = 'pink';

            }
        }
</script>
```

### 百度换肤

```javascript
 // 1. 获取元素 
        var imgs = document.querySelector('.baidu').querySelectorAll('img');
        // console.log(imgs);
        // 2. 循环注册事件 
        for (var i = 0; i < imgs.length; i++) {
            imgs[i].onclick = function() {
                // this.src 就是我们点击图片的路径   images/2.jpg
                // console.log(this.src);
                // 把这个路径 this.src 给body 就可以了
                document.body.style.backgroundImage = 'url(' + this.src + ')';
            }
        }
```

### 隔行换色

```java
var trs = document.querySelector('tbody').querySelectorAll('tr');
        for (var i = 0;i<trs.length;i++){
            trs[i].onmouseover = function(){
                this.className = "bg";
            }
            trs[i].onmouseout = function(){
                this.className = "";
            }
        }
```

### 单选全选

```javascript
 // 1. 全选和取消全选做法：  让下面所有复选框的checked属性（选中状态） 跟随 全选按钮即可
        // 获取元素
        var j_cbAll = document.getElementById('j_cbAll'); // 全选按钮
        var j_tbs = document.getElementById('j_tb').getElementsByTagName('input'); // 下面所有的复选框
        // 注册事件
        j_cbAll.onclick = function() {
                // this.checked 它可以得到当前复选框的选中状态如果是true 就是选中，如果是false 就是未选中
                console.log(this.checked);
                for (var i = 0; i < j_tbs.length; i++) {
                    j_tbs[i].checked = this.checked;
                }
            }
            // 2. 下面复选框需要全部选中， 上面全选才能选中做法： 给下面所有复选框绑定点击事件，每次点击，都要循环查看下面所有的复选框是否有没选中的，如果有一个没选中的， 上面全选就不选中。
        for (var i = 0; i < j_tbs.length; i++) {
            j_tbs[i].onclick = function() {
                // flag 控制全选按钮是否选中
                var flag = true;
                // 每次点击下面的复选框都要循环检查者4个小按钮是否全被选中
                for (var i = 0; i < j_tbs.length; i++) {
                    if (!j_tbs[i].checked) {
                        flag = false;
                        break; // 退出for循环 这样可以提高执行效率 因为只要有一个没有选中，剩下的就无需循环判断了
                    }
                }
                j_cbAll.checked = flag;
            }
        }
```

### 自定义属性

```javascript
 var div = document.querySelector('div');
        // 1. 获取元素的属性值
        // (1) element.属性
        console.log(div.id);
        //(2) element.getAttribute('属性')  get得到获取 attribute 属性的意思 我们程序员自己添加的属性我们称为自定义属性 index
        console.log(div.getAttribute('id'));
        console.log(div.getAttribute('index'));
        // 2. 设置元素属性值
        // (1) element.属性= '值'
        div.id = 'test';
        div.className = 'navs';
        // (2) element.setAttribute('属性', '值');  主要针对于自定义属性
        div.setAttribute('index', 2);
        div.setAttribute('class', 'footer'); // class 特殊  这里面写的就是class 不是className
        // 3 移除属性 removeAttribute(属性)    
        div.removeAttribute('index');
```

### tab切换

```javascript
// 获取元素
        var tab_list = document.querySelector('.tab_list');
        var lis = tab_list.querySelectorAll('li');
        var items = document.querySelectorAll('.item');
        // for循环绑定点击事件
        for (var i = 0; i < lis.length; i++) {
            // 开始给5个小li 设置索引号 
            lis[i].setAttribute('index', i);
            lis[i].onclick = function() {
                // 1. 上的模块选项卡，点击某一个，当前这一个底色会是红色，其余不变（排他思想） 修改类名的方式

                // 干掉所有人 其余的li清除 class 这个类
                for (var i = 0; i < lis.length; i++) {
                    lis[i].className = '';
                }
                // 留下我自己 
                this.className = 'current';
                // 2. 下面的显示内容模块
                var index = this.getAttribute('index');
                console.log(index);
                // 干掉所有人 让其余的item 这些div 隐藏
                for (var i = 0; i < items.length; i++) {
                    items[i].style.display = 'none';
                }
                // 留下我自己 让对应的item 显示出来
                items[index].style.display = 'block';
            }
        }
```

### 自定义属性

```javascript
<div getTime="20" data-index="2" data-list-name="andy"></div>
    <script>
        var div = document.querySelector('div');
        // console.log(div.getTime);
        console.log(div.getAttribute('getTime'));
        div.setAttribute('data-time', 20);
        console.log(div.getAttribute('data-index'));
        console.log(div.getAttribute('data-list-name'));
        // h5新增的获取自定义属性的方法 它只能获取data-开头的
        // dataset 是一个集合里面存放了所有以data开头的自定义属性
        console.log(div.dataset);
        console.log(div.dataset.index);
        console.log(div.dataset['index']);
        // 如果自定义属性里面有多个-链接的单词，我们获取的时候采取 驼峰命名法
        console.log(div.dataset.listName);
        console.log(div.dataset['listName']);
    </script>
```

### 节点概述

```javascript
一般的，节点至少拥有nodeType,nodeName,nodeValue这三个基本属性
元素节点 nodeType 为1
属性节点 nodeType 为2
文本节点 nodeType 为3
```

### 父节点操作

```javascript
<script>
        // 1. 父节点 parentNode
        var erweima = document.querySelector('.erweima');
        // var box = document.querySelector('.box');
        // 得到的是离元素最近的父级节点(亲爸爸) 如果找不到父节点就返回为 null
        console.log(erweima.parentNode);
    </script>
```

### 子节点操作

```javascript
<script>
        // DOM 提供的方法（API）获取
        var ul = document.querySelector('ul');
        var lis = ul.querySelectorAll('li');
        // 1. 子节点  childNodes 所有的子节点 包含 元素节点 文本节点等等
        console.log(ul.childNodes);
        console.log(ul.childNodes[0].nodeType);
        console.log(ul.childNodes[1].nodeType);
        // 2. children 获取所有的子元素节点 也是我们实际开发常用的
        console.log(ul.children);
    </script>
```

```javascript
  <script>
        var ol = document.querySelector('ol');
        // 1. firstChild 第一个子节点 不管是文本节点还是元素节点
        console.log(ol.firstChild);
        console.log(ol.lastChild);
        // 2. firstElementChild 返回第一个子元素节点 ie9才支持
        console.log(ol.firstElementChild);
        console.log(ol.lastElementChild);
        // 3. 实际开发的写法  既没有兼容性问题又返回第一个子元素
        console.log(ol.children[0]);
        console.log(ol.children[ol.children.length - 1]);
    </script>
```

### 兄弟节点

```javascript
 var div = document.querySelector('div');
        // 1.nextSibling 下一个兄弟节点 包含元素节点或者 文本节点等等
        console.log(div.nextSibling);
        console.log(div.previousSibling);
        // 2. nextElementSibling 得到下一个兄弟元素节点
        console.log(div.nextElementSibling);
        console.log(div.previousElementSibling);
```

### 创建节点

```javascript
// 1. 创建节点元素节点
        var li = document.createElement('li');
        // 2. 添加节点 node.appendChild(child)  node 父级  child 是子级 后面追加元素  类似于数组中的push
        var ul = document.querySelector('ul');
        ul.appendChild(li);
        // 3. 添加节点 node.insertBefore(child, 指定元素);
        var lili = document.createElement('li');
        ul.insertBefore(lili, ul.children[0]);
        // 4. 我们想要页面添加一个新的元素 ： 1. 创建元素 2. 添加元素
```

### 留言板案例

```javascript
 // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value;
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
            }
        }
```

### 删除节点

```javascript
 // 1.获取元素
        var ul = document.querySelector('ul');
        var btn = document.querySelector('button');
        // 2. 删除元素  node.removeChild(child)
        // ul.removeChild(ul.children[0]);
        // 3. 点击按钮依次删除里面的孩子
        btn.onclick = function() {
            if (ul.children.length == 0) {
                this.disabled = true;
            } else {
                ul.removeChild(ul.children[0]);
            }
        }
```

### 删除案例

```javascript
  // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value + "<a href='javascript:;'>删除</a>";
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
                // (3) 删除元素 删除的是当前链接的li  它的父亲
                var as = document.querySelectorAll('a');
                for (var i = 0; i < as.length; i++) {
                    as[i].onclick = function() {
                        // node.removeChild(child); 删除的是 li 当前a所在的li  this.parentNode;
                        ul.removeChild(this.parentNode);
                    }
                }
            }
        }
```

### 克隆节点

```javascript
var ul = document.querySelector('ul');
        // 1. node.cloneNode(); 括号为空或者里面是false 浅拷贝 只复制标签不复制里面的内容
        // 2. node.cloneNode(true); 括号为true 深拷贝 复制标签复制里面的内容
        var lili = ul.children[0].cloneNode(true);
        ul.appendChild(lili);
```

### 动态生成表单数据

```javascript
 // 2. 往tbody 里面创建行： 有几个人（通过数组的长度）我们就创建几行
        var tbody = document.querySelector('tbody');
        for (var i = 0; i < datas.length; i++) { // 外面的for循环管行 tr
            // 1. 创建 tr行
            var tr = document.createElement('tr');
            tbody.appendChild(tr);
            // 2. 行里面创建单元格(跟数据有关系的3个单元格) td 单元格的数量取决于每个对象里面的属性个数  for循环遍历对象 datas[i]
            for (var k in datas[i]) { // 里面的for循环管列 td
                // 创建单元格 
                var td = document.createElement('td');
                // 把对象里面的属性值 datas[i][k] 给 td  
                // console.log(datas[i][k]);
                td.innerHTML = datas[i][k];
                tr.appendChild(td);
            }
            // 3. 创建有删除2个字的单元格 
            var td = document.createElement('td');
            td.innerHTML = '<a href="javascript:;">删除 </a>';
            tr.appendChild(td);

        }
        // 4. 删除操作 开始 
        var as = document.querySelectorAll('a');
        for (var i = 0; i < as.length; i++) {
            as[i].onclick = function() {
                // 点击a 删除 当前a 所在的行(链接的爸爸的爸爸)  node.removeChild(child)  
                tbody.removeChild(this.parentNode.parentNode)
            }
        }
        // for(var k in obj) {
        //     k 得到的是属性名
        //     obj[k] 得到是属性值
        // }
```

### 效率测试

```javascript
<script>
    function fn() {
        var d1 = +new Date();
        var array = [];
        for (var i = 0; i < 1000; i++) {
            array.push('<div style="width:100px; height:2px; border:1px solid blue;"></div>');
        }
        document.body.innerHTML = array.join('');
        var d2 = +new Date();
        console.log(d2 - d1);
    }
    fn();
</script>
```

### 注册事件

```javascript
 var btns = document.querySelectorAll('button');
        // 1. 传统方式注册事件
        btns[0].onclick = function() {
            alert('hi');
        }
        btns[0].onclick = function() {
                alert('hao a u');
            }
            // 2. 事件侦听注册事件 addEventListener 
            // (1) 里面的事件类型是字符串 必定加引号 而且不带on
            // (2) 同一个元素 同一个事件可以添加多个侦听器（事件处理程序）
        btns[1].addEventListener('click', function() {
            alert(22);
        })
        btns[1].addEventListener('click', function() {
                alert(33);
            })
       
        })
```

### 删除事件

```javascript
<div>1</div>
    <div>2</div>
    <div>3</div>
    <script>
        var divs = document.querySelectorAll('div');
        divs[0].onclick = function() {
                alert(11);
                // 1. 传统方式删除事件
                divs[0].onclick = null;
            }
            // 2. removeEventListener 删除事件
        divs[1].addEventListener('click', fn) // 里面的fn 不需要调用加小括号
        function fn() {
            alert(22);
            divs[1].removeEventListener('click', fn);
        }
       
    </script>
```

### dom事件流

```javascript
 // dom 事件流 三个阶段
// 1. JS 代码中只能执行捕获或者冒泡其中的一个阶段。
// 2. onclick 和 attachEvent（ie） 只能得到冒泡阶段。       
// 3. 捕获阶段 如果addEventListener 第三个参数是 true 那么则处于捕获阶段  docu        
// 4. 冒泡阶段 如果addEventListener 第三个参数是 false 或者 省略 那么则处于冒泡阶段  son -> father ->body -> html -> document
 var son = document.querySelector('.son');
son.addEventListener('click', function() {
    alert('son');
}, false);
var father = document.querySelector('.father');
father.addEventListener('click', function() {
    alert('father');
}, false);
document.addEventListener('click', function() {
    alert('document');
})
三个alert 从上至下依次弹出
```

### 事件对象

```javascript
var div = document.querySelector('div');
        div.onclick = function(e) {
                // console.log(e);
                // console.log(window.event);
                // e = e || window.event;
                console.log(e);
            }
            // div.addEventListener('click', function(e) {
            //         console.log(e);

        //    })
// 1. event 就是一个事件对象 写到我们侦听函数的 小括号里面 当形参来看
        // 2. 事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数
        // 3. 事件对象 是 我们事件的一系列相关数据的集合 跟事件相关的 比如鼠标点击里面就包含了鼠标的相关信息，鼠标坐标啊，如果是键盘事件里面就包含的键盘事件的信息 比如 判断用户按下了那个键
        // 4. 这个事件对象我们可以自己命名 比如 event 、 evt、 e
        // 5. 事件对象也有兼容性问题 ie678 通过 window.event 兼容性的写法  e = e || window.even
```

### 事件对象

```javascript
<div>123</div>
    <ul>
        <li>abc</li>
        <li>abc</li>
        <li>abc</li>
    </ul>
    <script>
        // 常见事件对象的属性和方法
        // 1. e.target 返回的是触发事件的对象（元素）  this 返回的是绑定事件的对象（元素）
        // 区别 ： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁
        var div = document.querySelector('div');
        div.addEventListener('click', function(e) {
            console.log(e.target);
            console.log(this);

        })
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
                // 我们给ul 绑定了事件  那么this 就指向ul  
                console.log(this);
                console.log(e.currentTarget);

                // e.target 指向我们点击的那个对象 谁触发了这个事件 我们点击的是li e.target 指向的就是li
                console.log(e.target);

            })
```

### 阻止默认行为

```javascript
 // 2. 阻止默认行为（事件） 让链接不跳转 或者让提交按钮不提交
        var a = document.querySelector('a');
        a.addEventListener('click', function(e) {
                e.preventDefault(); //  dom 标准写法
            })
```

### 阻止事件冒泡

```java
var son = document.querySelector('.son');
son.addEventListener('click', function(e) {
    alert('son');
    e.stopPropagation(); // stop 停止  Propagation 传播
    e.cancelBubble = true; // 非标准 cancel 取消 bubble 泡泡
}, false);
```

### 事件委托

```javascript
<body>
    <ul>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
    </ul>
    <script>
        var ul = document.querySelector("ul");
        ul.addEventListener("click",function(e){
            e.target.style.backgroundColor = "pink"
        })
    </script>
</body>
```

### 鼠标事件

```javascript
var pic = document.querySelector('img');
document.addEventListener('mousemove', function(e) {
    // 1. mousemove只要我们鼠标移动1px 就会触发这个事件
    // console.log(1);
    // 2.核心原理： 每次鼠标移动，我们都会获得最新的鼠标坐标， 把这个x和y坐标做为图片的top和left 值就可以移动图片
    var x = e.pageX;
    var y = e.pageY;
    console.log('x坐标是' + x, 'y坐标是' + y);
    //3 . 千万不要忘记给left 和top 添加px 单位
    pic.style.left = x - 50 + 'px';
    pic.style.top = y - 40 + 'px';
```

### 键盘对象

```javascript
document.addEventListener('keyup', function() {
    console.log('我弹起了');
})

//3. keypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头啊
document.addEventListener('keypress', function() {
    console.log('我按下了press');
})
//2. keydown 按键按下的时候触发  能识别功能键 比如 ctrl shift 左右箭头啊
document.addEventListener('keydown', function() {
    console.log('我按下了down');
})
// 4. 三个事件的执行顺序  keydown -- keypress -- keyup
```

### 键盘对象

```javascript
// 键盘事件对象中的keyCode属性可以得到相应键的ASCII码值
// 1. 我们的keyup 和keydown事件不区分字母大小写  a 和 A 得到的都是65
// 2. 我们的keypress 事件 区分字母大小写  a  97 和 A 得到的是65
document.addEventListener('keyup', function(e) {
    // console.log(e);
    console.log('up:' + e.keyCode);
    // 我们可以利用keycode返回的ASCII码值来判断用户按下了那个键
    if (e.keyCode === 65) {
        alert('您按下的a键');
    } else {
        alert('您没有按下a键')
    }

})
document.addEventListener('keypress', function(e) {
    // console.log(e);
    console.log('press:' + e.keyCode);

})
```

### 京东输入案例

```javascript
// 核心思路： 检测用户是否按下了s 键，如果按下s 键，就把光标定位到搜索框里面
// 使用键盘事件对象里面的keyCode 判断用户按下的是否是s键
// 搜索框获得焦点： 使用 js 里面的 focus() 方法
var search = document.querySelector('input');
document.addEventListener('keyup', function(e) {
    // console.log(e.keyCode);
    if (e.keyCode === 83) {
        search.focus();
    }
})
```

### window事件

```javascript
window.addEventListener('load', function() {
    var btn = document.querySelector('button');
    btn.addEventListener('click', function() {
        alert('点击我');
    })
})
window.addEventListener('load', function() {

    alert(22);
})
document.addEventListener('DOMContentLoaded', function() {
    alert(33);
})
// load 等页面内容全部加载完毕，包含页面dom元素 图片 flash  css 等等
// DOMContentLoaded 是DOM 加载完毕，不包含图片 falsh css 等就可以执行 加载速度比 load更快一些
```

### 调整窗口大小

```javascript
window.addEventListener('load', function() {
    var div = document.querySelector('div');
    window.addEventListener('resize', function() {
        console.log(window.innerWidth);

        console.log('变化了');
        if (window.innerWidth <= 800) {
            div.style.display = 'none';
        } else {
            div.style.display = 'block';
        }

    })
})
```

### 定时器以及清除定时器

```javascript
<button>停止爆炸</button>
<script>
    var btn = document.querySelector("button")
var timer = setTimeout(function(){
    console.log("爆炸了");
},5000)
btn.addEventListener('click',function(){
    clearTimeout(timer)
})
</script>
```

### 定时器

```javascript
<script>
    // 1. setInterval 
    // 语法规范：  window.setInterval(调用函数, 延时时间);
    setInterval(function() {
    console.log('继续输出');

}, 1000);
// 2. setTimeout  延时时间到了，就去调用这个回调函数，只调用一次 就结束了这个定时器
// 3. setInterval  每隔这个延时时间，就去调用这个回调函数，会调用很多次，重复调用这个函数
</script>
```



### 发送短信案例

```javascript
发送短信<input type="text"><button>发送</button>
<script>
    var btn = document.querySelector("button");
var time = 3;
btn.addEventListener('click',function() {
    btn.disabled = true;
    var timer = setInterval(function(){
        if(time==0){
            btn.disabled = false;
            clearTimeout(timer)
            btn.innerHTML = "发送"
        } else{
            btn.innerHTML = "还剩下" +time+"秒"
            time--
        }
    },1000)

    })
```

### location对象案例

```javascript
<button>点击</button>
<div></div>
<script>
    var btn = document.querySelector("button")
var div = document.querySelector("div")
var timer = 5
btn.addEventListener('click',function(){
    location.href = "http://www.itcast.cn"
})
setInterval(function(){
    if (timer==0){
        location.href = "http://www.itcast.cn"
    } else{
        div.innerHTML='您将在' + timer + '秒钟之后跳转到首页';
        timer--;
    }   
},1000)
</script>

location.href 获取域名
location.search 获取参数
```

### location常用方法

```javascript
var btn = document.querySelector('button');
btn.addEventListener('click', function() {
    // 记录浏览历史，所以可以实现后退功能
    // location.assign('http://www.itcast.cn');
    // 不记录浏览历史，所以不可以实现后退功能
    // location.replace('http://www.itcast.cn');
    location.reload(true);
})
```

### history 对象

```javascript
history.back() 后退
history.forword() 前进
```

### offset偏移

```javascript
<div class="father">
    <div class="son"></div>
</div>
<div class="w"></div>
<script>
    // offset 系列
    var father = document.querySelector('.father');
var son = document.querySelector('.son');
// 1.可以得到元素的偏移 位置 返回的不带单位的数值  
console.log(father.offsetTop);
console.log(father.offsetLeft);
// 它以带有定位的父亲为准  如果么有父亲或者父亲没有定位 则以 body 为准
console.log(son.offsetLeft);
var w = document.querySelector('.w');
// 2.可以得到元素的大小 宽度和高度 是包含padding + border + width 
console.log(w.offsetWidth);
console.log(w.offsetHeight);
// 3. 返回带有定位的父亲 否则返回的是body
console.log(son.offsetParent); // 返回带有定位的父亲 否则返回的是body
console.log(son.parentNode); // 返回父亲 是最近一级的父亲 亲爸爸 不管父亲有没有定位
</script>
```

### offset与style

```javascript
offset:
获取任意样式表的样式
获取的数值没有单位
offsetWidth 包含 padding+border+width
只读属性不能赋值
style：
只能获取行内
获取的带单位的字符串
不包含padding+border
可读写属性

```

