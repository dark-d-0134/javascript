## script元素

script元素用于在html文档中嵌入javascript代码，也可以用于引入外部的js文件。
```html title="script元素" {cmd=true} 
<script>
    // javascript代码
    function sayHello() {
        alert("Hello World!");
    }

</script>
```

```html title="引入外部文件" {cmd=true} 
<script src="js文件路径"></script>
```
### script元素的属性

| 属性        | 说明                                                                                                               |
| :---------- | :----------------------------------------------------------------------------------------------------------------- |
| async       | 可选。表示应该立即开始下载脚本，但不应妨碍页面中的其他操作，比如下载资源或等待加载其他脚本。只对外部脚本文件有效。 |
| charset     | 可选。表示通过src属性指定的代码的字符集。                                                                          |
| crossorigin | 可选。配置相关请求的CORS（跨域资源共享）设置。                                                                     |
| defer       | 可选。表示脚本可以延迟到文档完全被解析和显示之后再执行。只对外部脚本文件有效。                                     |
| integrity   | 可选。允许比较接收到的资源和指纹以验证它们。                                                                       |
| language    | 已废弃。请改用type属性。                                                                                           |
| src         | 可选。表示包含要执行代码的外部文件。                                                                               |
| type        | 可选。表示代码块中脚本语言的内容类型（也称为MIME类型）。默认值为"text/javascript"。                                |

### script元素的执行顺序
script元素按文档所处位置顺序依次解析和执行。解析器在解析到script元素时，会暂停文档的解析，执行完script元素中的代码后，再继续解析文档。  
当然也有可能在解析script元素时，遇到了src属性，这时候浏览器会并行下载src属性指定的文件，但不会阻塞文档的解析。

## 标签的位置
script元素可以放在html文档的任何位置，但是一般放在head元素中或者body元素中的最后。
``` html title="推荐写法" {cmd=true}
<html>
    <head>
    </head>
    <body>
        <!-- 网页内容 -->
        <!-- ... -->

        <!-- 将js代码都写到body元素的最后面 -->
        <script>
            // javascript代码
            function sayHello() {
                alert("Hello World!");
            }
        </script>
    </body>
</html>
```    

