	//存取的是上一次的xhr对象
		let lastXhr;
	    if(lastXhr){
	//取消本次请求（此时取消的是上一次的请求）
	      lastXhr.abort()
	    }
	    lastXhr = getCode('GET','http://localhost:3000/code')
  
	//获取验证码的方法
		function getCode(method,url) {
	    
		    let xhr = new XMLHttpRequest()
		    
		    xhr.onreadystatechange = function () {
		      if(xhr.readyState === 4 && xhr.status === 200){
		        console.log(xhr.responseText)
		      }
		    }
		    
		    xhr.open(method,url)
		    
		    xhr.send()
		    
		    return xhr
	    
		}