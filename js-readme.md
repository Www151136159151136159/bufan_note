## js基础知识

(```)
<!-- 1.内嵌式 -->
	<script>
		// 1.弹窗 不常用,测试可以使用
		// alert()这是一个方法 用于弹窗
		// 今天... 输入弹窗的内容 是 "字符串"类型的,必须加引号,可以是'',也可是""
		alert('今天天气不错!');
		alert("今天天气不错!");
		// alert(今天天气不错!);
		</script>
	<!-- 2.外链式 -->
	<script type="text/javascript" src="main.js"></script>
(```)

**一行代码结束 一定要加; 分号是给js解析器解析用的**

(```)
<script>
	// confirm 返回了两种状态 boolean 布尔类型 true/false
		if(confirm('你确定要走?')){
			alert('你走吧,永远不要回来!');
		}else{
			alert('咱们结婚吧!');
		}
		</script>
(```)

**document.write('这是一段话...'); 输出的是一段话**

**变量是用var声明的 名称随便起**

(```)
<script>
		// 字符串类型
		var str = '今天天不错!';
		// 在算术里  = 计算结果的 
		// 1 + 1 = 2;
		// 变量的命名规范
		// var  12 = '张三';    错误
		// var 变量1 =  '张胜男';  错误
		// var *132 = '张三'; 除了_  和  $ 之外的
		var var = '张三' ;  关键词 ; 关键词不是绝对性词汇(left/red)
		// var Str = '今天不错啊!';  严格区分大小写的
		console.log(str);
		</script>
(```)

(```)
<script>
		var name = '张三';
		var age = 20;
		// typeof 可以判断 "基本数据类型"
		console.log(typeof  name);  // string
		console.log(typeof  age);  // number
		</script>
(```)

**// +  -  *   /   %(求余)**

(```)
<script>
		console.log(1+2);
		注意: 
			+  1. 字符串+num ==> 拼接为字符串
			+  2. 字符串+字符串 ==> 拼接为字符串 (在所有的编程语言中,拼接是用的最多的操作)
			-  3. num-字符串类型的数字 ==> number
			-  4. 字符串类型number - 字符串类型number ==> number
			-  5. num-字符串(非number) ==> NaN(not  a  number);而且NaN!=NaN
			/  6.  1/0 = Infinity   无限大 
		</script>
(```)

**基础语法都是ECMAScript**

(```)
<script>
	1. 基本数据类型
		String Number  boolean  undefined  null
	2. 变量声明
		var  注意: 虽然js是弱类型语言,但是在使用的时候,必须明确的直达数据类型.
	3. 输出方式
		alert()
		console.log() 开发调试使用
		prompt()  弹窗输入框
		confirm()  确认对话框
		document.write()  在网页中输入
	4. 算术运算符
		+  -  * /  % 
		a)  +  可是计算,也可是连接符(比较常用)
		b)  +  number+String ==> String(拼接)
		c)  - number-String(num) ==> number(计算) ; 3- '1' = 2;
		d)  -  number- String(!num)  ==> NaN(计算,错误);  3-'a' = NaN; NaN!= NaN;
		e)  /  1/0= Infinite...错误
	5. 比较运算符
		> < >= <=  !=  ==  ===(恒等于)
		a)  3 > '2' ?   true   隐式转换
	6. 简写
		a = a+b ==>  a+=b;  
		a = a+1 ==>  a+= 1;  ==> a++;
		注意: a++ 是先参与使用,后++
			  ++a  是先执行++,再参与使用
	7.在程序里,包含了一部分属性和功能的集合,我们称之为对象.
	</script>
(```)

(```)
<script>
 		Math对象和Date对象不同的是 Math里的都是静态方法,不需要new
		// 1.天花板函数 向上取整
		console.log(Math.ceil(2.1));  // 3
		console.log(Math.ceil(-2.1));  // -2
		//2.地板函数
		console.log(Math.floor(-2.1));  // -3
 		// 3. max 求最大值 Math.max(3,7,2,8)
 		// 4. min 最小值
 		// 5. Math.random() 区间:[0,1)
 		console.log(Math.random());
 		// 6.求1-10 随机数  [1-11) 
 		console.log(Math.floor(Math.random()*10+1));
 		// 7. 任意区间 比如  15-31?     *个数+最小值
 		console.log('15-31之间随机值: ',Math.floor(Math.random()*17+15));
 		// 8. Math.pow(x,y)
 		// 9. Math.round(x) 四舍五入 但是不推荐使用
 		</script>
(```)

**从输入框获取的都是字符串类型**

**如果是通过对"枚举类型"的判断,用switch比较清晰**

(```)
<script>
		switch (parseInt(fruitNum)) { 
			case 1:
				alert('苹果');
				break;
			case 2:
				alert('香蕉');
				break;
			default:
				alert('没有这个编号!');
				break;
				</script>
(```)

**while用法**

(```)
<script>
		var num = 1;
		//需要有跳出条件
		while (num < 10) {
			console.log('num==>',num);
			num ++ ;
		}
		</script>
(```)

**dowhile用法**

(```)
<script>
	do{
			console.log('num2==>',num);
		}while(num!=1)
		</script>
(```)

**for循环**

+ for循环 
	- 是可以嵌套的
	- 嵌套循环 : 内部的变量不能和外部一样 

(```)
<script>
		var num = 10;
		// 遍历0~99
		// 如果存在 i == num 结束循环
		for(var i = 0 ; i < 100 ; i ++){
			console.log('i==>',i);
			if(num == i){
				console.log('结束循环...');
				// 一旦break 循环体被结束,当前循环体内部break后面的代码也不再执行.
				break;
			}
			console.log('么么哒!');
		}
		console.log('end  for....');
		</script>
(```)

**continue;结束本次循环,后面的代码不再执行**


**数组和下标**

(```)
<script>
// 1.通过对象形式创建数组
		var arr = new Array();
		// 数组的下标是从0开始的
		arr[0] = 30;
		arr[1] = 22;
		arr[2] = 33;
		// 2. 直接创建空数组
		var arr2 = [25,33,44,70];
		console.log(arr);
		//可通过下标赋值 也可以通过下标取值
		console.log('arr[2]==>',arr[2]);
		console.log(arr2);
		console.log('arr2[2]==>',arr2[2]);
		// arr 是一个对象  xx.abc  abc是xx的属性;  xx.def() def是xx的方法
		console.log('数组的length==>',arr2.length);
		// jqx.name;  jqx.run();
		</script>
(```)

**for ... in用法**

(```)
<script>
// 数组里面的值 可以是任意类型
		// 但是组好是同一类数据
		var arr = [1,3,12,34,7];
		// 不要出现下标越界的情况
		for(var i = 0 ; i < arr.length ; i++){
			console.log('下标为'+i,arr[i]);
		}
		console.log('=================');
		// for ... in
		for(var a in arr){
			console.log(arr[a])
		}
		</script>
(```)


**拼接 转换 打断**

(```)
<script>
		var arr = [1,2,3];
		var arr2 = [4,5,6];
		// 1. concat() 拼接 并不会影响原来的数组
		var arr3 = arr.concat(arr2);
		console.log(arr);
		console.log(arr3);
		 // 2. join() 把数组转换为字符串,默认是,
		 var arr4 = ['a','b','c'];
		console.log(arr4.join(','));
		// 3. split() 把字符串打断为数组
		var str = 'it is a fineday today';
		var arr5 = str.split(' ');
		console.log(arr5);
		//遍历所有的编号
		var code = '1101,1110,111,111,10101';
		var codeArr = code.split(',');
		for(var i = 0 ;i < codeArr.length ; i++){
			console.log(codeArr[i]);
		}
		</script>
(```)

**push unshift pop shift的使用**

(```)
<script>
		var arr = [1,2,3];
		// 1. push()   从后面推进去一个新元素
		// 2. unshift()  从数组的前面放入一个新元素
		// 3. pop()    删除最后一个元素
		// 4. shift()   删除第一个元素
		arr.push(4);
		arr.push(5);
		arr.unshift(0);
		console.log(arr);
		arr.pop();
		console.log(arr);
		</script>
(```)

**冒泡排序（Bubble Sort），是一种计算机科学领域的较简单的排序算法。它重复地走访过要排序的元素列，依次比较两个相邻的元素，如果他们的顺序（如从大到小、首字母从A到Z）错误就把他们交换过来。走访元素的工作是重复地进行直到没有相邻元素需要交换，也就是说该元素已经排序完成。**

(```)
<script>
		var arr = [8,5,4,3,2];
	    for(var j = 1 ; j < arr.length ; j ++){
	    	for(var i = 0 ; i < arr.length-j ; i++){
	    		if(arr[i]>arr[i+1]){
	    			//交换位置
	    			var temp = arr[i];
	    			arr[i] = arr[i+1];
	    			arr[i+1] = temp;
	    		}
	    	}
    		console.log('第'+j+'轮的结果',arr);
	    }
	    console.log('最终结果',arr);
	    </script>
(```)

**选择排序（Selection sort）是一种简单直观的排序算法。它的工作原理是每一次从待排序的数据元素中选出最小（或最大）的一个元素，存放在序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到全部待排序的数据元素排完。 选择排序是不稳定的排序方法。**

(```)
<script>
	var arr = [1,8,5,7,4,3,2];
		// 0 1 2 3 4 
		for(var j = 0 ; j < arr.length-1 ; j++){
			// 默认最小值的下标为 0 
			var minIndex = j;
			for(var i = 1+j ; i < arr.length ; i ++){
				if(arr[minIndex]>arr[i]){
					//让贤
					minIndex = i;
				}
			}
			//如果最小下标依然是j 就没必要交换位置
			if(j!=minIndex){
				//放到第一个位置
				var temp = arr[j];
				arr[j] = arr[minIndex];
				arr[minIndex] = temp;
			}		
			console.log('获取了最小下标为'+minIndex);
			console.log(arr);
		}
		console.log('最终结果为:',arr);
		</script>
(```)

**求平均值**

(```)
<script>
	var arr = [33,21,1,40,12,5] 
		var sum = 0 ;
		for(var i = 0 ; i < arr.length ; i++){
			sum += arr[i];
		}
		console.log(sum/arr.length);
		</script>
(```)

**函数如果不调用是不会执行的**

+ 函数
	- 为什么需要函数? 原因:可以封装一部分功能,帮我解决重复问题
	- js是面向过程编程 特点是: 继承  封装  多态  ,函数本身就是封装的体现

	- 自定义函数 可以先使用,后声明
		function  say(){
			alert('hello,world!');
		}
	- 匿名函数  必须先声明,后使用
		var run = function(){
			alert('Hi  i  am  running...');
		}
		run();
	- 平时用那种?  自定义
(```)
<script>
		function add (x,y) {
			// alert(x+y);
			// 返回函数的执行结果 可以外部使用
			// return 之后的代码不再执行!!
			return x+y;
			console.log('么么哒!');
		}
		//弹出3,5的结果
		var sum = add(3,5);
		alert(sum);
		// 打印3,5的结果
		console.log(sum);
		</script>
(```)

**script标签可以认为是js的window对象**
+ 函数作用域: 
	- 在window对象里声明的变量,在函数里都可以使用
	- 函数内部不能调用其他函数内部的变量
	- 在window作用域不能调用函数内部的变量

(```)
<script>
		var name = '张三';
		function say () {
			var age = 20;
			alert('Hi '+name);
		}
		function run(){
			alert('Hi '+name+',my age is '+age);
		}	
		say();
		// alert(age);
		run();
		</script>
(```)

***
***





## js算法程序案例

## 封装函数
***面积和周长的计算  Math.PI=3.1415926...***

(```)
<script>
		function  area(r) {
			return Math.PI*Math.pow(r,2);
		}
		function length(r){
			return 2*Math.PI*r;
		}
</script>
(```)

+ 三元表达式
	- return x>y?x:y; 意思是:当x>y时,取x值;否则取y值;
	- var rs = 3>12?'ok':'not ok!';

***求一组数中的最大值和最小值(先排序)***

(```)
<script>
		var arr = [3,5,7,0,1,20];		
		alert(getMax(arr));
		function getMax (arr) {
			var maxIndex = 0;
			for(var i = 1 ; i < arr.length ;i ++){
				if(arr[maxIndex]<arr[i]){
					maxIndex = i;
				}
			}
			console.log('max==>',arr[maxIndex]);
			return arr[maxIndex];
		}
		</script>
(```)

***
**翻转数组，返回一个新数组**

+ 方法1
(```)
<script>
		var arr = ['a','b','c','d','e'];
		function reverse (arr) {
			// 数组是先进后出
			var arr2 = [];
			for(var i = arr.length-1 ; i>=0 ; i--){
				// 从后面加入新元素
				arr2.push(arr[i]);
			}
			return arr2;
		}
		console.log(reverse(arr));
		</script>
(```)

+ 方法2	
(```)	
<script>
		function reverse2(arr){
			for(var i = 0 ; i < Math.floor(arr.length/2) ; i++){
				var temp = arr[i];
				arr[i] = arr[arr.length-1-i];
				arr[arr.length-1-i] = temp;
			}
			return arr;
		}
		console.log(reverse2(arr));
		</script>
(```)

**求5的阶乘**

(```)
<script>
		function jcDg(n){
			if(n==1){
				return 1;
			}
			return n*jcDg(n-1);
		}
		//递归  不适合很大的数 会造成内存溢出
		// alert(jc(5));
		alert(jcDg(5));
		</script>
(```)
			
+ 递归  
	- 什么情况下用到递归? 比如文件的查找
	- 不适合很大的数 会造成内存溢出
	- 递归要有跳出条件


**求1!+2!+3!+....+n!**

(```)
<script>
		function jc (n) {
			//跳出条件
			if(n==1){
				return 1;
			}
			return n*jc(n-1);
		}
		function jcSum(n){
			var sum = 0 ;
			for(var i = 1 ; i <= n ; i ++){
				sum += jc(i);
			}
			return sum;
		}
		// 1+1*2+1*2*3+1*2*3*4+120
		alert(jcSum(5));
		</script>
(```)

**素数 只能被1和自己整除的数**

(```)
<script>
		function  isSu (n) {
			//标记法
			var flag = true;
			for(var i = 2 ; i < n; i ++){
				//刚好除尽
				if(n%i == 0){
					console.log('至少能被'+i+'整除!');
					flag = false;
					break;
				}
			}
			return flag;
		}
		alert(isSu(923));
		</script>
(```)

**有一对兔子，从出生起后第3个月起每个月都生一对兔子，小兔子长到第三个月后每个月又生一对兔子， 假如兔子都不死，问第二十个月的兔子对数为多少？ 不死神兔**
		// 1  1
		// 2  1
		// 3  2
		// 4  3
		// 5  5
		// 6  8	
		// 7  13
		// 8   21
		// ..
		// 斐波那切数列
		// 1.递归

(```)
<script>
		function fb (n) {
			if(n==1 || n==2){
				return 1;
			}
			return fb(n-1)+fb(n-2);
		}
		alert(fb(20));
		// 1  fb(1)  1
		// 2  fb(2)  1
		// 3  fb(3)  fb(1)+fb(2)
		// 4  fb(4)  fb(3)+fb(2)
		// ...
		// n  fb(n)  fb(n-1)+fb(n-2)	
		</script>	
(```)


**2、输入某年某月某日，判断这一天是这一年的第几天？（闰年）
（四年一闰，百年不闰，四百年在闰）
只有在闰年的时候366天  在2月29天多一天
其余的时间2月都是28
1.是否是闰年
2.每个月多少天**
+ 获取年月日 字符串类型

(```)
<script>
		var dateStr = prompt('请输入年月日: ','2019-01-24');
		alert('您输入的日期: '+dateStr+'在当前年份属于第'+getDayCount(dateStr)+'天');
		function getDayCount(dateStr){
			// 2. 把年月日字符串转换为日期类型  Object类型  2012-03-20
			var date = new Date(dateStr);
			// 3. 闰年
			// alert(isRun(2000));
			// 4. 获取每一个月的天数
			var monthDays = [31,28,31,30,31,30,31,31,30,31,30,31];
			var year = date.getFullYear();
			// 0 , 1 , 2  , 3 
			var month = date.getMonth(); // 2
			var day = date.getDate();
			var rs = day;
			console.log(rs);
			for(var i = 0 ; i < month ; i ++){
				rs += monthDays[i];
			}
			if(month>1){
				if(isRun(year)){
					rs ++;
				}
			}
			return rs;
		}
		function isRun (year) {
			// var flag = false;
			// if(year%100==0){
			// 	flag = (year%400==0);
			// }else{
			// 	flag = year%4==0;
			// }
			return year%400==0 || (year%100!=0&&year%4==0);
		}
		</script>
(```)

(```)
<script>
		function say () {
			alert('Hi my name is zhangsan!');
		}
		// say 本质是函数体
		console.log(say);
		</script>
(```)

(```)
<script>	
		var num1 = 10;
		var num2 = 20;
		// 形参就相当于 函数的局部变量
		function add(num1,num2){
			return num1+num2;
		}
		function sub(num1,num2){
			return num1-num2;
		}
		</script>
(```)

**如果只需要封装一个代码块  只需要执行一次 那么不需要变量名**

+ 自执行函数前面加分号. 原因:如果进行压缩,代码不会连在一起
(```)
<script>
		;(function(){
			console.log('hello,world!');
		})();
		</script>
(```)


(```)
<script>
		function foo (name,fn) {
			alert(name+ '啦啦啦');
			fn(name);
		}
		// 函数能做参数吗?
		function bar(name){
			alert('Hi,'+name+',么么哒!');
		}
		// 函数体 本身也能作为参数传递,这种称之为 回调函数(了解)
		// 在处理异步的情况使用最多
		foo('张三',bar);
</script>
(```)