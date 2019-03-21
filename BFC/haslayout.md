###什么是haslayout
	layout是windows IE的一个私有概念，它决定了元素如何对其内容定位和尺寸计算，
	以及与其他元素的关系和相互作用。当一个元素“拥有布局”时，它会负责本身及其子元素的尺寸和定位。
	而如果一个元素“没有拥有布局”，那么它的尺寸和位置由最近的拥有布局的祖先元素控制。
	
	必须说明的是，IE8及以上浏览器使用了全新的显示引擎，已经不在使用haslayout属性，
	因此haslayout属性只针对IE6和IE7。
	
###为什么会有haslayout
	理论上说，每个元素都应该控制自己的尺寸和定位，即每个元素都应该“拥有布局”，当然这只是理想状态。
	而对于早期的IE显示引擎来说，如果所有元素都“拥有布局”的话，会导致很大的性能问题。
	因此IE开发团队决定使用布局概念来减少浏览器的性能开销，即只将布局应用于实际需要的那些元素，
	所以便出现了“拥有布局”和“没有拥有布局”两种情况。
	
###默认拥有布局的元素
	html, body, table, tr, td, img, hr,
	input, select, textarea, button,
	iframe, embed, object, applet, marquee
	
###怎么触发haslayout
	float: left或right
	display: inline-block
	position: absolute
	width: 除auto外任何值
	height: 除auto外任何值
	zoom: 除normal外任何值(zoom: 1无法在IE5.0中触发haslayout)
	writing-mode: tb-rl
	
	在IE7中，以下属性也可以触发元素的haslayout
		min-height: 任意值
		min-width: 任意值
		max-height: 除none 外任意值
		max-width: 除none 外任意值
		overflow: 除visible外任意值，仅用于块级元素
		overflow-x: 除visible 外任意值，仅用于块级元素
		overflow-y: 除visible 外任意值，仅用于块级元素
		position: fixed
	
