get请求和post请求的区别
get请求
1、可传输的数据量较小
2、不是很安全，因为发送请求时会将参数直接放在地址栏
3、请求参数在请求首行
4、get请求会自动使用缓存（在现代浏览器和IE浏览器中有一定区别，IE中是强制缓存，其他浏览器中是协商缓存）
post请求
1、数据量比get大
2、较为安全，请求参数未被暴露
3、请求参数位于请求体中
4、post请求默认不会使用缓存，即每次请求都需要访问服务器