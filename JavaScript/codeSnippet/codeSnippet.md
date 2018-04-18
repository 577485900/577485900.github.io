# 循环绑定事件
1. 获取所有节点
    ```
    var nodes = document.querySelectorAll('ul li');
    ```
2. 输出 click5
    ```
    for (var i=0, len=nodes.length;i<len;i++){
        nodes[i].addEventListener('click',function () {
            alert('click'+i)
        })
    }
    ```
3. 输出 click0 - click4
    ```
    for(var i=0,len=nodes.length;i<len;i++){
        //不加！会报错
        //布尔运算符使其变成表达式
        //(function(){})()
        !function (node,index) {
            node.addEventListener('click',function () {
                alert('click'+index)
            })
        }(nodes[i],i)
    }
    ```
4. 输出 click0 - click4
    ```
    // NodeList.prototype.forEach并非所有浏览器支持
    // [].slice.call(nodes)浅拷贝
    [].slice.call(nodes).forEach(function (node,index) {
        node.addEventListener('click',function () {
            alert('click'+index)
        })
    })
    ```
5. 输出 click0 - click4
    ```
    // 块级作用域
    for (let i=0, len=nodes.length;i<len;i++){
        nodes[i].addEventListener('click',function () {
            alert('click'+i)
        })
    }
    ```