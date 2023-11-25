## shell

### ps aux" 可以查看系统中所有的进程；

### "ps -le" 可以查看系统中所有的进程，而且还能看到进程的父进程的 PID 和进程优先级；

### "ps -l" 只能看到当前 Shell 产生的进程；

### netstat -napt：TCP 的连接状态

### route -n：查看当前路由表

### 查看内存

https://www.51cto.com/article/719609.html`<br>`

### 查看io

iostat：`<br>`iotop：`<br>`pidstat：`<br>`

### lsof

用于查看你进程开打的文件，打开文件的进程，进程打开的端口(TCP、UDP)。找回/恢复删除的文件。是十分方便的系统监视工具，因为 lsof 需要访问核心内存和各种文件,硬件，所以需要root用户执行。`<br>`实例13：列出所有的网络连接`<br>`命令：lsof -i`<br>`实例14：列出所有tcp 网络连接信息`<br>`命令：lsof -i tcp`<br>`实例15：列出所有udp网络连接信息`<br>`命令：lsof -i udp`<br>`实例16：列出谁在使用某个端口`<br>`

### df

disk free . 命令用于显示目前在 Linux 系统上的文件系统磁盘使用情况统计。`<br>`tar -cvf 创建归档文件`<br>`tar -xvf 解除归档文件(还原)`<br>`tar -tvf 查看归档文件内容`<br>`![](https://secure2.wostatic.cn/static/oBAgzjKSUzpyy1rejM47Rm/截屏2023-09-23 21.43.22.png?auth_key=1700739545-fvySmWXTt8nsx1oLBT9yWG-0-fdcd7a29ccb0ec2ef67541920bd84ee8)`<br>`![](https://secure2.wostatic.cn/static/izZ4Q2QxTDem2gK8k2id4X/截屏2023-09-23 21.43.36.png?auth_key=1700739546-dqbNxL6UGgvfAz8Z2QGbQQ-0-b471d80698ea408d29d507f9642bc0ab)`<br>`

### find

find命令功能非常强大，通常用来在特定的目录下搜索符合条件的文件，也可以用来搜索特定用户属主的文件。`<br><b>`按文件名查询：使用参数 -name`</b><br>``<b>`命令：find + 路径 + -name +“文件名”`</b><br>`示例：find /home -name “a.txt”`<br><b>`按文件大小查询：使用参数 -size`</b><br>`命令：find + 路径 + -size + 范围`<br>`范围`<br>`Ø 大于：+表示 -- +100k`<br>`Ø 小于：-表示 -- -100k`<br>`Ø 等于: 不需要添加符号 -- 100k`<br>`大小`<br>`Ø M 必须大写（10M）`<br>`Ø k 必须小写（20k）`<br>`例子: 查询目录为家目录`<br>`等于100k的文件: find ~/ -size 100k`<br>`大于100k的文件: find ~/ -size +100k`<br>`大于50k, 小于100k的文件: find ~/ -size +50k -size -100k`<br><b>`按文件类型查询：使用参数 -type`</b><br>`命令：find + 路径 + -type + 类型`<br>`类型`<br>`Ø 普通文件类型用 `<b>`f`</b>` 表示而不是-`<br>`Ø d -目录`<br>`Ø l -符号链接`<br>`Ø b -块设备文件`<br>`Ø c -字符设备文件`<br>`Ø s -socket文件，网络套接字`<br>`Ø p -管道`<br>`查找指定目录下的普通文件： find /home -type f`<br>`查找根目录下所有的普通文件`<br>`deng@itcast:~$ find / -type f<br>查找根目录中所有的目录稳步<br>deng@itcast:~$ find / -type d`<br>`查找根目录所有的字符设备`<br>`deng@itcast:~$ find / -type c<br>查找根目录下所有的块设备<br>deng@itcast:~$ find / -type b`<br>`查找根目录下所有的符号链接`<br>`deng@itcast:~$ find / -type l<br>查找根目录下所有的套接字<br>deng@itcast:~$ find / -type s`<br>`查找根目录下所有的管道`<br>`deng@itcast:~$ find / -type p`<br>`

### grep

Linux系统中grep命令是一种强大的文本搜索工具，grep允许对文本文件进行模式查找。如果找到匹配模式， grep打印包含模式的所有行。`<br>`grep一般格式为：`<br><b>`grep [-选项] ‘搜索内容串’ 文件名`</b><br>`在grep命令中输入字符串参数时，最好引号或双引号括起来。例如：grep ‘a ’1.txt。`<br>`常用选项说明：`<br>`| `<b>`选项`</b>` | `<b>`含义`</b>`                                 |
| -------- | ---------------------------------------- |
| -v       | 显示不包含匹配文本的所有行（相当于求反） |
| -n       | 显示匹配行及行号                         |
| -i       | 忽略大小写                               |`<br>`命令：grep -r + “查找的关键字” + 路径`<br>`搜索目录需要添加参数： -r`<br>`查找 /home/itcast 下包含“hello，world“字符串的文件`<br>`grep -r "hello，world" /home/itcast`<br>`示例：`<br>`grep -a hello /bin/ls 将二进制文件以文本文件的方式搜索hello grep -i hello /etc/passwd 在/etc/passwd文件里找hello并且忽略大小写查找 grep -n hello /etc/passwd 搜索hello结果并显示在文件里出现的行号 grep -w hello /etc/passwd 搜索完全匹配hello单词的行 grep -v hello /etc/passwd 显示出在/etc/passwd文件里没有hello的行 grep -r hello /etc/ 在/etc/目录里所有文件里找hello并显示结果 grep -i hello /etc/passwd --color=auto 在/etc/passwd文件中找hello并且忽略大小写，然后高亮显示匹配的关键字`<br>`

### 如何检查内存泄漏