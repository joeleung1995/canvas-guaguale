# canvas-guaguale
## 基于canvas的刮刮乐项目  
## 技术栈：canvas，dom  
## 思路：  
1 创建一个画布，准备好几张图片作为背景，利用Math.random来随即设置画布的背景  
2 用‘画笔’将画布填充一层‘蒙版’  
3 利用‘画笔’属性globalCompositeOperation为"destination-out"的特性（在源图像外显示目标图像。只有源图像外的目标图像部分会被显示，源图像是透明的），实现新的路径会在‘蒙版’透明显示，露出下面的背景  
4 利用dom操作‘画笔’，监听鼠标移动事件，实现“挂”的动作  
5 监听mouseup事件，如果剩下的‘蒙版’剩下面积不足30%，则‘蒙版’被全部清除  
## 难点：  
1 需要决绝画笔路径很直，看起来很僵硬的问题；解决方案：在监听mousemove事件时，创建一个previous-position来即时更新‘画笔’路径的起始位置  
2 计算‘蒙版’剩余面积；解决方案：利用‘画笔’的内置getImageData方法，获取图像信息，再利用rgba是否为透明判断。  
