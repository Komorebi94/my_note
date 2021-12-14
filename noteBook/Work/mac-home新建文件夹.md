### MAC在home下新建文件夹：Operation not supported

> + sudo vim /etc/auto_master
>
>     ```
>     #
>     # Automounter master map
>     #
>     +auto_master            # Use directory service
>     /net                    -hosts          -nobrowse,hidefromfinder,nosuid
>     /home                   auto_home       -nobrowse,hidefromfinder
>     /Network/Servers        -fstab
>     /-                      -static
>     ```
>
> + 注释掉 /home这一行
>
> + cd /
>
> + sudo automount

