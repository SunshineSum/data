###拖拽实现思路

	1.实现思路：
		拿到元素一开始的位置，拿到鼠标的偏移量，将鼠标的偏移量加到元素身上
	2.注意点
		-在onmouseup中我们需要清除onmousemove的逻辑
			如果不清除的话，onmousemove的逻辑仍然会被触发，因为onmousemove在pc端可以被单独触发
			当然我们最好把onmouseup的逻辑也清除掉，保证一次操作的完整性，也避免重复定义onmouseup事件
	
		-onmousemove必须嵌套在onmousedown中
			因为onmousemove在pc端可以单独触发，导致我们onmousemove的逻辑在没有onmousedown时就触发了	
		
		-onmousemove必须绑定在doucument身上
			因为我们很有可能拖出到元素外，导致逻辑不能被触发。所以不能绑定在拖拽元素身上

		-onmouseup必须绑定在doucument身上
			因为我们页面中会存在层级比较高的元素，可能会导致我们onmouseup的逻辑不被触发。
			所以不能绑定在拖拽元素身上

	3.关于细节
		-鼠标的偏移是相对于视口的
		-元素的偏移是相对于parentNode的
		-拖拽元素的偏移量在整个过程中是覆盖的并不是叠加
		-不需要考虑拖拽的方向，偏移量的正负值可以代表方向
		
