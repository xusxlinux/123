```ini

[program:xx]                                                      ; [program:xx]是被管理的进程配置参数，xx是进程的名称
command=/opt/apache-tomcat-8.0.35/bin/catalina.sh run             ; 程序启动命令
startsecs=10                                                      ; 启动10秒后没有异常退出，就表示进程正常启动了，默认为1秒
autostart=true                                                    ; 在supervisord启动的时候也自动启动
autorestart=true                                                  ; 程序退出后自动重启,可选值：[unexpected,true,false]，默认为unexpected，表示进程意外杀死后才重启
startretries=3                                                    ; 启动失败自动重试次数，默认是3
user=tomcat                                                       ; 用哪个用户启动进程，默认是root
priority=999                                                      ; 进程启动优先级，默认999，值小的优先启动
redirect_stderr=true                                              ; 把stderr重定向到stdout，默认false
stdout_logfile_maxbytes=20MB                                      ; stdout 日志文件大小，默认50MB
stdout_logfile_backups = 20                                       ; stdout 日志文件备份数，默认是10
stdout_logfile=/opt/apache-tomcat-8.0.35/logs/catalina.out        ; stdout 日志文件，需要注意当指定目录不存在时无法正常启动，所以需要手动创建目录（supervisord 会自动创建日志文件）
stopasgroup=true                                                  ; 默认为false,进程被杀死时，是否向这个进程组发送stop信号，包括子进程
killasgroup=true                                                  ; 默认为false，向进程组发送kill信号，包括子进程
```
