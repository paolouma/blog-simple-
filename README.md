# blog-simple-

演示地址：http://www.tianmawenzi.com/blog/

一个自适应不同尺寸设备的博客系统，会根据大小不同屏幕加载不同的css布局。

设计思路：
<meta name="viewport" content="width=device-width, initial-scale=1.0">
 
  <link rel="stylesheet" href="css/main.css">
  <link rel="stylesheet" media="(max-width: 768px)" href="css/mobile.css">
  
  
通过媒体查询浏览器的宽度给出不同的css文件。党浏览器宽度大于768px时候加载main.css，当浏览器宽度小于768px时候用mobile.css覆盖main.css，实现对小尺寸设备的个性化显示设置。


main.css：

.left{
	position: fixed;
	float: left;
	width:20%;
	border-right: 2px white solid;
}

.main{
	float: right;
	width:80%;

}

.article{
	margin:10px 20% 30px 20px;
	background: #6c6c6c;
	padding: 10px;

}


把主页分成左边栏和右边主体两部分。左右边栏宽度分别为20%和80%。宽屏状态下，主体main部分中的article设置右边margin为20%，防止浏览器过度拉宽每行文字过长。


mobile.css：

.left{
	 position: relative;
	float: none;
	width:100%;
	
}

.main{

    
	width:100%;
	/*border: 5px white solid;*/
}

.article{
	margin:10px 20px 30px 20px;
	background: gray;
	padding: 10px;

}
当小尺寸设备访问时候，为节省宽度，设定左边栏left和主体main的尺寸都为100%，这样它们就会上下排列。同时为了充分利用宽度，article的右边margin设定为较小的20px。


菜单设置：
宽屏时候，菜单放在左边栏显示。窄屏访问时候，菜单默认为隐藏（display：none）状态，点击右上角的 菜单 可以唤出。
需要说明的是，这个效果不是通过js实现的，而是通过纯css实现的。
具体就是，菜单这两个字实际是一个label，关联到一个默认隐藏的CheckBox。点击菜单，CheckBox被激活，css设置checkbox处于checked状态时候，菜单状态由隐藏变为显示状态（display：block）。
