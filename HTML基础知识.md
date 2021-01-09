#URI和URL
>**URI**：统一资源标志符，包括URL和URN(统一资源名称，无定位效果)
>**URL**：统一资源定位符

***
#请求Request
1.	内容:
	>- 请求方法Request Method
	>- 请求的网址Request URL
		   - URL，唯一确定想要的资源
	>- 请求头Request Headers
		   -  用来说明服务器要使用的附加信息，如Cookie，Referer，Use-Agent
	>- 请求体Request Body
2.	常见请求方法Request Methods
>- GET
>    - 在浏览器中直接输入URL并回车，便发起了一个GET请求，请求的参数会直接包含到URL中
>- POST
>    - 大多在表单提交时发起，数据、参数以表单形式传输，不会体现在URL中
>    
>GET和POST区别：
>GET参数包含在URL中，POST以表单传输，包含在请求体中
>GET请求提交的数据最多1024字节，POST请求没有限制

1.	HTTP1.0有三种请求方法:GET,POST,HEAD
HTTP1.1新增6种:OPTIONS、PUT、PATCH、DELETE、TRACE、CONNECT


| 序号 	     |	 方法      |	描述    |
| :--------: | :--------: | :------: |
|	1	|GET	|请求指定的页面信息，并返回实体主体|
|	2	|	HEAD|	类似于 GET 请求，只不过返回的响应中没有具体的内容，用于获取报头|
|	3	|	POST|	向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST 请求可能会导致新的资源的建立和/或已有资源的修改。|
|	4	|	PUT|	从客户端向服务器传送的数据取代指定的文档的内容。|
|	5	|	DELETE|	请求服务器删除指定的页面。|
|	6	|	CONNECT|	HTTP/1.1 协议中预留给能够将连接改为管道方式的代理服务器。|
|	7	|	OPTIONS|允许客户端查看服务器的性能。|
|	8	|	TRACE|	回显服务器收到的请求，主要用于测试或诊断。|
|	9	|	PATCH|	是对 PUT 方法的补充，用来对已知资源进行局部更新 。|

***

#	常用请求头Request Headers
>1. Accept：请求报头域，指定客户端可接受哪些类型的信息
>2. Accept-Language：指定客户端可接受的语言类型
>3. Accept-Encoding：指定客户端可接受的内容编码
>4. Host：指定请求资源的主机IP和端口号，其内容为请求URL的原始服务器或网关的位置(从HTTP1.1开始，请求必须包含此内容)
>5. Cookie：网站为了辨别用户进行会话跟踪而存储在用户本地的数据，主要功能是维持当前会话。Cookie中有信息标识了我们所对应服务器的会话，每次浏览器在请求该站点的页面时，在请求头中加入Cookie并发给服务器，服务器识别出用户并查出当前处于登录状态时返回登录后才能看到的网页内容。
>6. Referer：标识这个请求从哪个页面发过来的，服务器可以拿到这个信息做处理如来源统计、防盗链处理
>7. User-Agent：简称UA，使服务器识别客户使用的操作系统和版本、浏览器及版本等信息，做爬虫时加上UA可以伪装成浏览器
>8. Content-Type：互联网媒体类型或MIME类型，在HTTP协议消息头中用来表示具体请求中的媒体类型信息，如text/html表示HTML格式，image/gif代表GIF图片，application/json表示JSON类型等。

- 请求体一般承载POST请求中的表单数据，对于GET请求请求体为空  

| Content-Type|    提交数据的方式 | 
| :--------: | :--------:|
| application/x-www-form-urlencoded |   表单数据 |
|multipart/form-data|表单文件上传|
|application/json|序列化json数据|
|text/xml|XML数据|
 


***

#响应Response
>1.	内容：
>- 响应状态码Response Status Code
表示服务器的响应状态
>- 响应头Response Headers
包含服务器对请求的应答信息
>- 响应体Response Body
>1.	响应头
>- Date：标识响应产生的时间
>- Last-Modified：最后修改时间
>- Content-Encoding：响应内容编码
>- Server：服务器信息，如名称、版本号
>- Content-Type
>- Set-Cookie：设置Cookies，告诉浏览器需要将此内容放在Cookies中，下次请求携带Cookies请求
>- Expires：响应过期时间
>1.	响应体
响应的正文数据都在响应体中。
爬虫请求网页后要解析的内容就是响应体
