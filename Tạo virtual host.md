# THIẾT LẬP VIRTUAL HOST

## APACHE

Thiết lập cấu hình virtual host trên 2 file chính

**※ File config (*.conf) của dịch vụ Apache**

``` ssh
<VirtualHost *:80> 
  DocumentRoot "D:/_App/localhost/laragon/www/new_project"
  ServerName new-project.test
  ServerAlias *.new-project.test
  <Directory "D:/_App/localhost/laragon/www/new_project">
    AllowOverride All
    Require all granted
  </Directory>
</VirtualHost>
```


**※ File host trên windows**

Đường dẫn mở file host:
C:\Windows\System32\drivers\etc\hosts

``` ssh
127.0.0.1 new-project.test
```
