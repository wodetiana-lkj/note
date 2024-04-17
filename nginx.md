
# 基础配置

```nginx
http {
    include mime.types;

    server {
        listen 80; # 监听端口
        server_name localhost; # 服务名称
        root html; # 根目录
        index index.html; # 默认访问文件
        
        location /app { # 匹配前缀
            root html/app; # location可覆写根目录
            index new.html; # 覆写默认文件
        }
    }
}
```

location匹配规则

- `=` 完全匹配
- `^~` 前缀匹配
- `~` `~*` 正则匹配 *代表是否区分大小写
