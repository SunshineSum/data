###鼠标滚轮事件

		ie/chrome : onmousewheel(dom0)
			event.wheelDelta
				上：120
				下：-120
			
		firefox : DOMMouseScroll 必须用(dom2的标准模式)
			event.detail
				上：-3
				下：3
				
		return false阻止的是  dom0 所触发的默认行为
		dom2 需要通过event下面的event.preventDefault();