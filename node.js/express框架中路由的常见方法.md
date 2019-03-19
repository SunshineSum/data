##express框架中路由的常见方法：	

> 一、request(请求对象上)

	*     -request.query  get请求查询字符串的参数，拿到的是一个对象
	*     -request.params get请求路由的参数，拿到的是一个对象
	*     -request.body post请求体的参数，拿到的是一个对象（要借助一个中间件）
	*     -request.get() 获取请求头


> 二、response(响应对象)

	*     -response.send()    给浏览器做出一个响应
	*     -response.end()     给浏览器做出一个响应（容易乱码）
	*     -response.download(相对路径)  告诉浏览器下载一个文件
	*     -response.sendFile(绝对路径) 给浏览器发送一个文件（浏览器会自动打开）
	*     -response.redirect(完整地址) 重定向到一个新的地址（url）
	*     -response.set('demo',123)  自定义响应头内容
	*     -response.get('demo') 获取响应头指定key对应的value（自定义的响应头一定能拿得到）