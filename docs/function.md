# 常用函数学习笔记
BY BUDUAN
QQ 2393982461
### 介绍
这个笔记记录我常用的函数的使用方法。

### JSON操作
此处仅对常用方法进行简要说明，详细参考：PHP手册：JavaScript对象符号（JSON）
#### json_encode
将数组转化成json形式的字符串。常用于：向前端发送数据前，将数组转化为json的形式等。  
输出类型``string``
使用案例：
```php
$a = array(
    'a' => 'AB',
    'b' => 'BC'
);
$b = json_encode($a);
echo $b;
```
输出内容：
```json
{"a":"AB","b":"BC"}
```
#### json_decode
将一个json字符串转化为对象/数组。常用于：处理Api接口传到服务器的json字符串等。  
输出类型``All``
参数：当assoc参数为true时，输出的是数组Array而不是对象Object

使用案例：
```php
$a = json_decode('{"a":"AB","b":"BC"}',true);
```
用``var_dump``输出数组后：
```
F:\www\note\jsonde.php:3:
array (size=2)
  'a' => string 'AB' (length=2)
  'b' => string 'BC' (length=2)
```
### 更多字符串操作
关于字符串：[http://php.docs.461blog.cn/#/php?id=字符串](http://php.docs.461blog.cn/#/php?id=字符串)  
详细参考：PHP手册：字符串函数  

### 字符串加密
#### MD5
详细参考：PHP手册：字符串函数-md5  
md5加密是目前服务端最常用的一种字符串加密方式。  
定义：计算字符串的md5散列值  
常用于：储存用户密码、效验文件等  
MD5会将一个字符串转化为32字符的十六进制数字形式返回散列值。
使用案例：
```php
$a = 'Hello world';
echo md5($a);
```
输出内容：
```
3e25960a79dbc69b674cd4ec67a72c62
```
MD5的加密是不可逆的，也就是说我们无法把加密后的数据还原回去，我们只能将数据转化为MD5的形式进行储存。
