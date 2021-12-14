### proxy_pass分为两种

+ 一种是只包含IP和端口号的，这种称为不带URI的方式
    + proxy_pass http://127.0.0.1:8081
+ 另一种是包含路径的，这种称为带URI的方式
    + proxy_pass http://127.0.0.1:8081/
    + proxy_pass http://127.0.0.1:8081/xxx

### 示例一 不带URI的方式

```nginx
location /api/ {
	proxy_pass http://127.0.0.1:8081
}
```

访问路径：http://127.0.0.1/api/xxx => http://127.0.0.1:8081/api/xxx



### 示例二 带URI的方式

```nginx
location /api/ {
	proxy_pass http://127.0.0.1:8081/
}
```

访问路径：http://127.0.0.1/api/xxx => http://127.0.0.1:8081/xxx



> 总结： 不带URI的，访问路径拼接匹配字符，带URI的，访问路径不拼接匹配字符



### 测试

```nginx
location /api1/ {
	proxy_pass http://localhost:8081;
}
# http://localhost/api1/xxx -> http://localhost:8081/api1/xxx

location /api2/ {
	proxy_pass http://localhost:8081/;
}
# http://localhost/api2/xxx -> http://localhost:8081/xxx

location /api3 {
	proxy_pass http://localhost:8081;
}
# http://localhost/api3/xxx -> http://localhost:8081/api3/xxx

location /api4 {
	proxy_pass http://localhost:8081/;
}
# http://localhost/api4/xxx -> http://localhost:8081//xxx

```

