## day43

### css:层叠样式表

### 1.css引入方式

#### 1.1行内样式

```
<div id="box" style="background-color: darkgreen;">luwei</div>
```

#### 1.2内嵌式

```html
<style>
    #box{
        background-color: crimson;
    }
</style>
```

#### 1.3外接式

```html
<link rel="stylesheet" href="css/index.css">
```

三种引入方式优先级

```
行内样式>内嵌式和外接式
内嵌和外接要谁在后面，在后面的优先级高
```

### 2.css选择器

#### 2.1基础选择器

- id选择器

  代码中必须唯一。

  ```
  #box{
  	xxxx
  }
  <div class="active" id="box">luwei</div>
  ```

  

- 类选择器

  可以重复，归类，类也可以设置多个

  ```
  <style>
  	.box{
  		width:200px;
  		height:200px;
  		background-color:yellow;
  		}
  	.active{
  		border-radius: 200px;
  		}
  </style>
  <div class='box active'></div>
  <div class='box'></div>
  <div class='box'></div>
  ```

  语法：

  ```
  .xxx
  ```

- 标签选择器

  ```
  div{}
  p{}
  ul{}
  ol{}
  span{}
  input{}
  ```

#### 2.2高级选择器

		    <div id="box">
		        <div>
		            <div>
		                <div>
		                    <p>
		                        mjj
		                    </p>
		                </div>
		            </div>
		        </div>
		        <p>
		            wusir
		        </p>
		    </div>
- 后代选择器

  ```
  <style type="text/css">
  	#box p{
  		color:red;
  		}
  </style>
  #wusir mjj :red
  ```

- 子代选择器

  ```
  <style type="text/css">
  	#box>p{
  		color:yellow;
  		}
  </style>
  #wusir:yellow
  ```

  

- 组合选择器

  ```
  div,p,boby,html,ul,ol...{
  	padding:0
  	margin:0
  }
  ```

- 交集选择器

  ```
  div.active{
  	
  }
  ```

- 属性选择器

  层叠性和继承性

  继承性：在css有某些属性是可以继承下来，color，text-xxx.line-height,font-xxx是可以继承下

  权重比较规则：

  #重点：继承来的属性权重为0

  ```
  前提是选中了标签
  权重比较：
  	1.数选择器数量： id(100) 类(10) 标签(1) 谁大它的优先级高，如果一样大，后面会覆盖前面的属性
  	2.选中的标签的属性优先级大于继承来的属性，他们是没有可比性
  	3.同是继承的属性
  		3.1谁描述近，谁的优先级越高
  		3.2描述的一样近，这个时候才回归到数选择器的数量
  ```

### 3.css的盒模型

- width：内容的宽度
- height：内容的高度
- padding：内边距，border到内容的距离
- border：边框
- margin：外边距

HTML的嵌套关系

```
<!--块级标签：1.独占一行  2.可以设置宽高，如果不设置宽，默认是父标签的100%宽度-->
<!--行内标签：1.在一行内显示 2.不可以设置宽高，如果不设置宽高，默认是字体的大小
        行内块标签： 1.在一行内显示 2.可以设置宽高
        
   在网页中：
   行内转块和行内块是非常使用   
   
   display:
            inline
            inline-block
            block

    嵌套关系：
    块级标签可以嵌套块级和行内以及行内块
    p标签不要嵌套div，也不要嵌套p
       放置： a  img  表单控件
    行内标签尽量不要嵌套块级
-->
```

