###默认行为
	浏览器默认有拖拽的行为，实现与我们差不多，这样一来浏览器的默认行为会与我们的逻辑产生冲突
		主流浏览器底下，我们可以通过return false来解决这个问题
		ie8 以下，我们需要采用全局捕获这种形式来实现
		


###全局捕获
	全局捕获在ie底下才有实质性的作用
	在谷歌中完全不存在全局捕获
	在火狐中存在全局捕获，但其没有作用
	
			
	设置全局捕获：element.setCapture()
		在处理一个 mousedown 事件过程中调用这个方法来把全部的鼠标事件重新定向到这个元素，
		直到鼠标按钮被释放或者 document.releaseCapture() 被调用。
		
			
	释放全局捕获：document.releaseCapture()
		如果该 document 中的一个元素之上当前启用了鼠标捕获，则释放鼠标捕获。
		通过调用 element.setCapture() 实现在一个元素上启用鼠标捕获。
		

###getBoundingClientRect()
	 	返回值是一个 DOMRect 对象，这个对象是由该元素的 getClientRects() 方法返回的一组矩形的集合, 
	 	即：是与该元素相关的CSS 边框集合 。
	
		DOMRect 对象包含了一组用于描述边框的只读属性——left、top、right和bottom，
		单位为像素。
		除了 width 和 height 外的属性都是相对于视口的'左上角'位置而言的。
