# Laravel blog Learning
> Author : Alex  
> Date : 2018-02-27  


## 在windows系統使用Composer建立Laravel
### 安裝Composer
> Composer download - [Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe)

安裝完Composer  
系統管理員打開cmd 輸入 `composer`  
跑出Comoser字樣就是安裝成功了  

``` 
C:\Windows\system32>composer
```

![圖片參考名稱](https://github.com/kewlnes1000/Laravel-blog/blob/master/readmeIMG/ComposerSuccess.png "ComposerSuccess")

### 建立Laravel資料夾
cmd cd 到 xampp  
創建一個名為blog的laravel項目   

```
C:\Windows\system32>cd C:\xampp\htdocs\laraveltest
C:\xampp\htdocs\laraveltest>composer create-project laravel/laravel blog --prefer-dist
```

### xampp 修改配置
1. PHP版本需求 >= 5.5.9
2. 開啟C:\xampp\apache\conf\httpd.conf
```
啟用 LoadModule rewrite_module modules/mod_rewrite.so
啟用 LoadModule vhost_alias_module modules/mod_vhost_alias.so
啟用 Include conf/extra/httpd-vhosts.conf
更改 Directory 
    <Directory />
          AllowOverride none
          Require all denied
    </Directory>
 ```
 3. 開啟C:\xampp\apache\conf\extra\httpd-vhosts.conf
 ```
 新增域名 blog.hd
     <VirtualHost *:80>
        ServerAdmin webmaster@dummy-host2.example.com
        DocumentRoot "C:/xampp/htdocs/laraveltest/blog"
        ServerName blog.hd
        ErrorLog "logs/dummy-host2.example.com-error.log"
        CustomLog "logs/dummy-host2.example.com-access.log" common
    </VirtualHost>
 ```
 4. 開啟PHP擴展 C:\xampp\php\php.ini
```
啟用 extension=php_openssl.dll
啟用 extension=php_pdo_mysql.dll
啟用 extension=php_mbstring.dll
```
 ### Laravel項目設置
 開啟 Laravel項目的資料夾  
 更改 `server.php` 為 `index.php`  
 複製偽靜態文件 `blog/public/.htaccess` 到 `blog/`  

 ### 開啟 xampp 打開瀏覽器輸入 blog.hd
 設置成功會出現 Laravel 字樣 如下

 ![圖片參考名稱](https://github.com/kewlnes1000/Laravel-blog/blob/master/readmeIMG/LaravelSuccess.png "LaravelSuccess")
