### root

配置段：http、server、location、if

处理结果：root路径 + location路径

```
location ^~ /t/ {
	root /www/root/html/;
}
```

请求：/t/a.html => /www/root/html/t/a.html

### alias

配置段：location

处理结果：alias路径替换location路径

```
location ^~ /t/ {
	alias /www/root/html/new_t/;
}
```

请求： /t/a.html => /www/root/html/new_t/a.html



> + 使用alias时，目录名后面一定要加“/”
> + alias在使用正则匹配时，必须捕捉要匹配的内容并在指定的内容处使用
> + alias只能在location块中使用