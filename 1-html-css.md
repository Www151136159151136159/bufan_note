+ GitHub:Initialized empty Git repository 
+ 意思是:已初始化空Git存储库


## html


+ html不区分大小写,但是尽量使用小写. 注释不能嵌套. 标签必须完整. 标签可以嵌套. 
+ 标签的属性必须加双引号.
+ <html> 页面的跟标签,一个页面只能有一个跟标签. 其余所有的内容 都应该写在html标签内部.
+ <head> 这里的内容不会在浏览器中直接显示, 该标签用于辅助浏览器解析页面.
	- <meta> 用于设置网页的元数据, 比如使用的字符集编码等 <meta charset="utf-8">
	- 用于设置关键字 <meta name="keywords" content="xxx" />
	- 用于描述信息 <meta name="description" content="xxxx" />
+ <title> 用于设置页面显示的标题, 在浏览器的选项卡头部显示, 可能对seo有帮助.


+ <body>
	- 用于设置网页的主题, 网页中所展示的所有内容 都在body中.
	- 注意: body中的多个换行和多个空格都会被当做一个空格来处理.


+ <br> 换行标签(一般不用)
+ <hr> 分割线
+ <strong> 加粗
+ <sup> 上标 例子: 5<sup>2</sup> 5的平方
+ <sub> 下标 例子: H<sub>2</sub>O 水的化学表达


### 无序列表
+ <ul>
	- <li>

### 有序列表
+ <ol>
	- <li>

### 自定义列表(类似于文章结构)
+ <dl>
	- <dt>
		- <dd>


+ ctrl+enter 迅速定位下一行
+ ctrl+/ 变成注释内容


+ 表单必须写到 <form> </form> 中
+ action 用于设置提交请求的地址
+ method 提交的方式
	- get是表单的默认提交方式 
		1. 地址栏显示提交内容
		2. 不安全
		3. 提交的内容容量有限
		4. 有缓存
	- post提交
		1. 数据在请求体保存
		2. 相对安全
		3. 容量无限
		4. 么有缓存


+ <input> 标签中type属性
	- 文本: text
	- 密码: password
	- 单选: radio  
	- 多选: checkbox
	- 头像: file    name=avatar	multiple 可以实现多选
	- 多行文本: textarea 
	- 提交: submit
	- 重置: reset
+ <lable> 用于包括输入框的头部和输入框 使之成为一体.多用于单选和多选
+ <select> <option></option> </select> 下拉框


+ disabled 不可点击
+ hidden 隐藏
+ readonly 只读
+ checked 默认选中
+ rowspan="数字" 控制所占行数
+ colspan="..." 控制所占列数
+ border="..."边框往内宽度
+ table标签 中属性   align 表示表格位置 可选择有 left center right
+ tr>th  tr>td
+ bgcolor 背景色


## css


+ # 访问的是id
+ . 访问的是class
+ 任何标签都有id属性,id在当前页面不能重复
+ 表单特有属性: name用于标识当前表单作用,用于向后台传递数据
+ 如果需要用表单给后台提交数据 必须有name属性
+ cellspacing 单元格间隔
+ cellpadding  文字和单元格之间的间距


+ 相同选择器,后面覆盖前面样式
+ 不同选择器需要对比权重大小
	- class选择器>标签选择器
	- id选择器>class选择器
	- 内部样式> id选择器
+ 显示器的三原色
	- r red
	- g green
	- b blue


+ 外部引入样式(开发使用) 
	- <link rel="stylesheet" type="text/css" href="style.css">


+ 交集选择器    
	1. 交集选择器 
		- .p1.danger{ }
	2. 并集选择器 
		- .p1,.p2{}  
	3. 后代选择器 .p1 a{} 
		- .d1 .p1 a{}


+ font-family: '楷体'
+ 尽量使用英文表示
+ 属性是没有先后顺序的,但是一般会有约定俗称的习惯
+ 因为浏览器不同,默认字体也不同.为了使字体保持统一,所以尽量在css中优先声明字体
+ text-indent em基于当前字体大小的倍数
+ font-style: italic;斜体
+ 行高的单位百分比 指的是基于字体的大小的百分比
	- 具体px  60px
	- 百分比倍数 200%
	- 直接写倍数 2
+ line-height: 30px;

+ 背景图片的平铺方式
	- background-repeat: no-repeat;

+ 图片位置
	- 如果只写一个属性 另一个为默认居中
	- 两个属性 
	- 具体值  坐标点基于左上角

+ 固定背景图片
	- background-attachment: fixed;

### css的盒子模型


+ 盒子边框  border
+ border 边框 border: 30px solid blue;
	- border-width: 30px;
	- border-style: solid
	- border-color: blue;

+ 盒子与盒子之间的间距 margin
+ margin
	- margin: xxx auto; 可以使元素居中.
	- 嵌套崩塌: 两个盒子发生嵌套的时候, 给子类设置margin会给父类造成一种崩塌现象, 子类的margin-top 没有效果, 而直接作用到父类.
	- 解决方案: 1. 给父类设置 overflow:hidden; 2. 给父类设置极小的padding;(一般不使用).
	- 重叠: 如果垂直两个块状元素同时设置了margin-bottom和margin-top, 那么这两个值将会发生重叠, 不会累加, 哪个值大用哪个.

+ 盒子填充物  padding
+ margin语法和padding一模一样

+ body有一个默认的padding
+ 为了保持浏览器的统一 一般会把所有的标签的margin和padding优先置0.
+ 超出部分隐藏
	overflow: hidden;
+ 可以控制元素显示或者隐藏
	display: none;


+ 根据标签的表现形式,把标签分类 


+ 块状标签 
	- 独占一行
	- 宽高有效 例子: div p br hr  table tr h1~h6 form
+ 行内块标签
	- 可以在同一行展示
	- 宽高有效 例子: img th  td  input select  textarea			
+行内标签
	- 可以在同一行展示
	- 宽高无效 例子: a span i em strong sup sub
			

+ <span>标签可以用于包括某一个元素 不具备任何样式 而且不会换行 是一个行内元素 

+ 不同的类型的标签的表现形式可以相互转换
	- 行内 ==> 行内块
	- 行内 ==> 块状
	- 行内块==> 行内
	- 行内块==> 块状
	- 块状==> 行内
	- 块状==> 行内块


+ display: none;	
+ visible/hidden
	- 都是隐藏元素,一个是隐藏了不占位置,而这个属性是隐藏了 占据原来的位置
	- visible 默认值
	- hidden  超出隐藏
	- auto  自动添加滚动条
	- scroll 硬添加  不常用
	- overflow: auto;


+ text-align  文字排版方式
+ text-indent  首行缩进
+ emmet快捷键 
	- (li.aside-item>a[href="#"]{手机_$ 手机卡})*10
+ 变为小手	
	- cursor: pointer; (pointer  move  help  default)
+ 恢复缩进
	- text-indent: 0;
+ 去掉下划线
	- text-decoration: none;
+ 用于去掉默认小黑点
	- list-style: none;
+ 去掉默认边框
	- border: none;
+ 去掉input输入框获取焦点默认边框
	- outline: none;
+ css3属性 用于控制背景图片宽高
	- background-size: 100% auto;
+ 希望鼠标悬浮的时候 修改样式  伪类:hover



### 浮动
> 浮动指的是使元素在脱离原来的文档流, 在父类元素中浮动起来.

 
+ 块级元素和行内元素都可以浮动, 当一个行内元素浮动以后将会自动变成一个块级元素.
+ 当一个块级元素浮动以后, 宽度会默认被内容撑开, 所以当漂浮一个块级元素时我们都会为其指定一个宽度.
+ 当一个元素浮动以后, 其下方的元素会上移. 元素中的内容将会围绕在元素的周围.
+ 浮动会使元素完全脱离文本流, 也就是不再在文档中占用位置.
+ 元素设置浮动以后,会一直向上漂浮直到遇到父元素的边界或者其他的浮动元素.
+ 元素浮动以后即完全脱离文档流, 这时不会再影响父元素的高度.也就是浮动元素不会撑开父元素.
+ 浮动元素默认会变为块元素, 即使设置displa:inline 以后其依然是个块元素.


+ float 浮动
	- 同级元素要浮动,都浮动!!
	- 左浮动
	- 右浮动 会造成元素顺序颠倒 尽量少用
+ 如果子类元素浮动了,而且高度比父类盒子大,那子类盒子的浮动会对后面的元素造成影响,这个我们称为浮动的影响;
	- clear:both; 不允许当前元素的左右有浮动元素 通常用于处理清除浮动造成的影响 
	- 如果父类没有写高度,子类盒子发生了浮动,可以设置父类盒子overflow:hidden;
+ 如果子类盒子没有设置浮动 而且父类盒子没有高度 则子类盒子会被父类盒子撑开


+ 页面布局的原则: 
	- 优先使用标准文档流
	- 标准文档流处理不了用浮动
	- 浮动处理不了用定位


+ 影响盒子大小的因素
	- border
	- padding 特殊: 继承的盒子在父盒子宽度范围内, padding值不会影响盒子该大小.


## 定位
> 通过postion属性 可以实现元素的定位. 元素定位之后,需要通过设置left和top值对元素定位.

	+ static 默认
	+ relative 相对定位. 相对元素本身的位置定位.
		- 当开启了相对定位以后, 可以使用top,bottom,left,right四个属性对元素进行定位.
		- 如果不设置元素的偏移量, 元素位置不会发生改变.
		- 相对定位不会使元素脱离文本流,元素在文本流中的位置不会改变.
		- 相对定位不会改变元素原来的特性.
		- 相对定位会使元素的层级提升, 使元素可以覆盖文本流中的元素.
	+ absolute 绝对定位
	+ fixed 固定定位


