##js基础知识

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
	// confirm 返回了两种状态 boolean 布尔类型 true/false
		if(confirm('你确定要走?')){
			alert('你走吧,永远不要回来!');
		}else{
			alert('咱们结婚吧!');
		}
(```)





















##js算法程序案例

## 封装函数
***面积和周长的计算  Math.PI=3.1415926...***

(```)
		function  area(r) {
			return Math.PI*Math.pow(r,2);
		}
		function length(r){
			return 2*Math.PI*r;
		}
(```)

+ 三元表达式
	- return x>y?x:y; 意思是:当x>y时,取x值;否则取y值;

***求一组数中的最大值和最小值(先排序)***

(```)
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
(```)
***
**翻转数组，返回一个新数组**

+ 方法1
(```)
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
(```)

+ 方法2	
(```)	
		function reverse2(arr){
			for(var i = 0 ; i < Math.floor(arr.length/2) ; i++){
				var temp = arr[i];
				arr[i] = arr[arr.length-1-i];
				arr[arr.length-1-i] = temp;
			}
			return arr;
		}
		console.log(reverse2(arr));
(```)

**求5的阶乘**

(```)
		function jcDg(n){
			if(n==1){
				return 1;
			}
			return n*jcDg(n-1);
		}
		//递归  不适合很大的数 会造成内存溢出
		// alert(jc(5));
		alert(jcDg(5));
(```)
			
+递归  
	- 什么情况下用到递归? 比如文件的查找
	- 不适合很大的数 会造成内存溢出
	- 递归要有跳出条件


**求1!+2!+3!+....+n!**

(```)
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
(```)

**素数 只能被1和自己整除的数**

(```)
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
(```)


**2、输入某年某月某日，判断这一天是这一年的第几天？（闰年）
（四年一闰，百年不闰，四百年在闰）
只有在闰年的时候366天  在2月29天多一天
其余的时间2月都是28
1.是否是闰年
2.每个月多少天**
+ 1. 获取年月日 字符串类型

(```)
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
(```)

(```)
		function say () {
			alert('Hi my name is zhangsan!');
		}
		// say 本质是函数体
		console.log(say);
(```)

(```)	
		var num1 = 10;
		var num2 = 20;
		// 形参就相当于 函数的局部变量
		function add(num1,num2){
			return num1+num2;
		}
		function sub(num1,num2){
			return num1-num2;
		}
(```)

**如果只需要封装一个代码块  只需要执行一次 那么不需要变量名**

+ 自执行函数前面加分号. 原因:如果进行压缩,代码不会连在一起
(```)
		;(function(){
			console.log('hello,world!');
		})();
(```)


(```)
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
(```)