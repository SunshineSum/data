##Http状态码（服务器给客户端的东西）

###作用：  
    告诉客户端，当前服务器处理请求的结果（过程）
    
###http状态码的分类
	 * 1xx : 服务器已经收到了本次请求，但是还需要进一步的处理才可以。
	 * 2xx : 服务器已经完整的接收到了客户端的请求，并且已经进入到：分析、理解.....最终处理完毕
	 * 3xx : 服务器已经接收到了请求，还需要其他的资源，或者指定新的东西返回，甚至交给其他服务器处理
	 * 4xx ：一般指请求的参数或者地址有错误， 出现了服务器无法理解的请求（前端的锅）
	 * 5xx ：服务器内部错误（不是因为请求地址或者请求参数不当造成的），无法响应用户请求（后端人员的锅）
 
###常见的几个状态码
	 * 200 ：成功
	 * 302 ：请求地址的重定向，服务器将你的请求重新定向到一个新的地址，搜索引擎会保留旧地址里面的内容
	 * 304 ：请求资源重定向到缓存中
	 * 404 ：资源未找到
	 * 500 ：服务器内部错误
	 * 502 ：连接服务器失败（服务器在处理一个请求的时候，或许需要其他的服务器配合，但是联系不上其他的服务器了）


 ## http协议？

	* 是什么？中文名字：超文本传输协议
	* 特点：无状态，但是cookie这样一个东西，去解决无状态的问题（最开始）。
	* 作用：规定了客户端和服务器之间传递信息的规则（统称为报文，请求报文，响应报文）。
###版本：
    * http 1.0 （过去的老版本） 不支持长连接。
    * http 1.1  （主流版本） 支持长连接，但是并发数量相对小一些(5~8个)。
    * http 2.0  （最新版本） 并发量性对大一些（5~12个），但是兼容性不是很好。
    * https？https是在http基础上，对传输的数据进行了加密，协议本身安全性做的比http好。
###报文的组成：
    1. 报文首行
    2. 报文头
    3. 空行
    4. 报文体