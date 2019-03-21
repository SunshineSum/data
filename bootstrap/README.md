### 流体容器
### 固定容器
	阈值（1200:lg 992:md 768:sm xs）
		浏览器大于等于1200时  					 固定容器的宽度为1170   (1140加槽宽)
		浏览器大于等于992 小于等于1200时  		 固定容器的宽度为970	 （940加槽宽）
        浏览器大于等于768 小于等于992时    		 固定容器的宽度为750	 （720加槽宽）
        浏览器小于等于768时    				 固定容器的宽度为auto   （仍旧有槽宽）


###栅格源码解析
###容器
	容器的公共样式：
	  margin-right: auto; //盒子水平居中
	  margin-left: auto;
	  padding-left:  15px;
	  padding-right: 15px;
	固定容器根据阈值在宽度会自动做出响应

###行
	margin-left:  -15px;
  	margin-right: -15px;
 
###列
	第一步，渲染列的公共样式
		 .col-xs-1, .col-sm-1, .col-md-1, .col-lg-1,
		 .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2,
		                      ...
		 .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12{
		    position: relative;
		    min-height: 1px;
		    padding-left: 15px;
		    padding-right: 15px;
		 }
	
	第二步，细分列的等级
		1.让所有的列全部浮动起来
			.col-xs-1，.col-xs-2，.col-xs-3....，.col-xs-12{
			    float: left;
			}
			
		2.为一类阈值底下的12个等级分配width
			.col-xs-12{width:100%}
			.col-xs-11{width:11/12}
			...
			.col-xs-1{width: 1/12;}
			
		3.列排序
			.col-xs-pull-12{right:100%}
			.col-xs-pull-11{right:11/12}
			....
			.col-xs-pull-1{right:1/12}
			.col-xs-pull-0{right:auto}
			
			
			.col-xs-push-12{left:100%}
			.col-xs-push-11{left:11/12}
			....
			.col-xs-push-1{left:1/12}
			.col-xs-push-0{left:auto}
			
		4.列偏移
			.col-xs-offset-12{margin-left:100%}
			.col-xs-offset-11{margin-left:11/12}
			....
			.col-xs-offset-0{margin-left:0}

### 栅格系统盒模型设计的绝妙之处

	容器：两边拥有槽宽一半的padding
	行：两边拥有槽宽一半的负margin
	列：两边拥有槽宽一半的padding
	
	为了维护槽宽的规则
		列两边必须的拥有槽宽一半的padding
	为了抵消掉容器的padding
		行两边必须拥有槽宽一半的负margin
	为了能使容器完整的包裹住行
		容器两边必须拥有槽宽一半的padding