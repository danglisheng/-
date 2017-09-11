# Carousel
1、设计思想
 主要分两块：一块是用户鼠标未进入图片区域时，利用调用setInterval函数来周期性地显示和隐藏图片。<br/>
 另一块是鼠标进入图片区域后，通过绑定事件处理函数对用户的操作进行响应。<br/><br/>
2、具体实现
(1)用setInterval设定定时任务，每隔一秒切换一次图片。图片切换的方法是，遍历图片元素的数组，把所有的display属性都设为none,再把要显示的那张图片的display设为block。<br/>
(2)当用户操作触发mouseover事件时，用clearInterval取消定时任务；触发mouseout事件时，再用setInterval设定定时任务。<br/>
(3)当用户点击前进、后退按钮时，先判断当前位置(保存在全局变量position中)，然后在对position进行加减操作，调用显示函数。<br/>
(4)把图片索引区包裹在&lt;ul&gt;标签里，每个单独的索引放在&lt;li&gt;里，并与position相关联，通过给父元素ul绑定点击事件，来代理子元素的事件。当用户点击索引时，更新position,调用显示函数。
