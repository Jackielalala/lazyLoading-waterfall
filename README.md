## lazyLoading-waterfall
预览：https://jsbin.com/radequjama/edit?output
## 懒加载原理
给项目底部增加一个元素，通过判断该元素是否出现在视窗中决定图片是否再次加载
## 瀑布流原理
1. 给项目的父元素设为相对定位，然后将每个项目绝对定位
2. 项目的宽度设定，然后计算在页面中可以摆放的列数
3. 每一列的初始高度设为0，高度最小值设为0，最小列的序号设为0
4. 然后第一个项目摆放在最小列，即第一列
5. 然后将该项目的高度赋给第一列，其摆放的位置，left为项目的宽度乘以之前的最小列的序号，top为最小列的高度
6. 顺次摆放后面的元素即可
## 实现原理
1. html中首先写一个项目的模型
2. css中对应写其样式
3. js中首先判断用于定位的空的块级元素是否出现在窗口中，若出现在窗口中则调用发送ajax请求的函数（及懒加载）
4. 写一个可以发送ajax请求的函数，函数请求成功后调用对数据进行渲染拼装的函数，注意，在调用瀑布流函数时需要当图片加载成功后，再获取元素高度（瀑布流）
