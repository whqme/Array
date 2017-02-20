# Array
创建和访问数组及使用方法
## 数组 ##
数组：一组变量的集合，起一个统一的名字。
如何使用数组：创建   取值    赋值
创建：共四种

 1.  创建空数组：var 数组名=[]; var 数组名=new Array();
	   何时使用：暂时不知道数据内容，先创建空数组，再追加
 2. 创建同时初始化数组内容：var 数组名=[值1,值2,...]
           何时使用：创建时，就已经知道数组的内容  
 3. 创建指定元素个数的数组: var 数组名=new Array(n);创建一个新数组对象，同时初始化n个空元素
 4. 创建同时初始化数组内容：var 数组名=new Array(值1,值2,...)

```
var week=["日","一","二","三","四","五","六"];
            0   1    2   3    4    5    6
			console.log("今天星期"+week[5]);
```
数组中每个元素<==>一个变量: 用法和变量完全相同！
    2. 取值：获取数组中指定位置的元素内容
       下标：数组中标识每个元素位置的序号
           默认，自动从0开始，每个+1，到元素个数-1结束
       如何取值：var 元素的值=数组名[下标];
    3. 赋值：将新值放入指定位置的元素中保存
       如何赋值：数组名[下标]=新值;

    数组是引用类型的对象：
        数组名作为变量赋值或参数传递时，都是将地址值复制给对方
        后果，对方修改数组的内容，访问原数字名也会受影响

    null: 主动释放一个对象的引用。null本身是原始类型的值
    垃圾回收器：伴随主程序，同时运行的后台程序
                记录每个对象当前被引用的次数
              被引用的次数==0，垃圾回收器自动释放对象内存空间
    强烈建议：在使用完，较大对象后，主动赋值为null，总是好习惯
   
   4. 获取数组的元素个数：arr.length属性，不加圆括号
      固定套路：
　　　　　获得数组最后一个元素：arr[arr.length-1];
          向数组末尾追加一个新元素：arr[arr.length]=新值
        js中的数组 vs 其他语言中的数组：3个区别：
          1. 不限制元素的数据类型
          2. 不限制数组长度
          3. js的数组越界不会出错！
               赋值时：自动创建制定下标的元素，保存新值
                       length属性，会随最大下标而变化
               取值时：视图从没有的下标位置取值，返回undefined

    5. 遍历数组：从第0个元素开始，依次获取每个元素，
                 对每个元素执行相同的操作
           下标：遍历数组时，天生的循环变量！
                
```
            var emps=[];
			var input='';
			while((input=prompt("输入员工姓名"))!="exit"){
				emps[emps.length]=input;
			}
			console.log(emps);
```

```
            var arr=[2,5,4,6,7,9];
			function getMax(arr){
				var max=arr[0];
				for(var i=1;i<arr.length;i++){
					arr[i]>max&&(max=arr[i]);
				}
				return max;
			}
			console.log(getMax(arr));//获取数组中最大值
```

```
//获取元素下标的位置
			function indexOf(arr,elem){
				for(var i=0;i<arr.length;i++){
					if (arr[i]==elem) {
						return 1;
					} else{
						return -1;
					}
				}
			}
			var emps=["A","B","C","E"];
			console.log(indexOf(emps,prompt("输入要查找的姓名")));
```
//冒泡排序

```
                function myArr(arr){
				for(var i=0;i<arr.length;i++){
					for(var j=0;j<arr.length-i-1;j++){
						if(arr[j]>arr[j+1]){
							var temp=arr[j];
							arr[j]=arr[j+1];
							arr[j+1]=temp;
						}
					}
				}
			}
			var arr=[12,4,9,21,43,3];
			myArr(arr);
			console.log(arr);
```
## 关联数组 ##
数组的API：
关联数组(hash数组)：可自定义元素下标名称的数组（关联数组是字符串）
索引数组：自动从0开始分配连续不重复的序号下标
如何创建关联数组：2种方式：
      1. 先创建普通空数组，再追加自定义下标的元素
         var ym=[];
         ym["sname"]="MM";
         ym["A"]=81;
         ym["B"]=53; 
         ym["C"]=89;
    *关联数组的length属性失效*
    *关联数组中的key不能重复*
    关联(hash)数组优势：查找极快！和元素个数无关！
    
      2. 创建数组同时，初始化元素内容：
         var mm={"sname":"MM","A":81,"B":53,"C":89};
                   key    value
         关联数组中保存的是多个key/value对儿
                            键  值


   

