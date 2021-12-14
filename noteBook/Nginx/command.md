+ 默认启动

    ```
    ./sbin/nginx
    ```

+ 指定配置文件启动

    ```
    ./sbin/nginx -c tmp/nginx.conf
    ```

+ 指定nginx程序目录启动

    ```
    ./sbin/nginx -p /usr/local/nginx/
    ```

+ 快速停止

    ```
    ./sbin/nginx -s stop
    ```

+ 优雅停止

    ```
    ./sbin/nginx -s quit
    ```

+ 不停止刷新配置

    ```
    ./sbin/nginx -s reload
    ```

+ 检查配置文件是否正确

    ```
    ./sbin/nginx -t
    ```

    