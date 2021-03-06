离线安装方法
=========

> 安装过程出现任何问题可以加QQ群讨论

> QQ群: 137158108 验证信息: github

如果无法通过`composer`安装可以下载离线包 百度网盘 http://pan.baidu.com/s/1bonLAph#path=/yii2-extjs-rbac

安装包下载到项目根目录解压到当前文件夹即可

需要修改配置的文件
------------

```
vendor/                  
    composer/
        autoload_psr4.php       // composer自动加载配置
    yiisoft/
        extensions.php          // Yii扩展配置
```

`composer`自动加载配置
------------

文件路径: `vendor/composer/autoload_psr4.php`

```php
<?php

// autoload_psr4.php @generated by Composer

$vendorDir = dirname(dirname(__FILE__));
$baseDir = dirname($vendorDir);

return array(
    ...
    // 最后位置添加一行
    'wsl\\rbac\\' => array($vendorDir . '/myweishanli/yii2-extjs-rbac'),
);
```

Yii扩展配置
------------

文件路径: `vendor/yiisoft/extensions.php`

```php
<?php

$vendorDir = dirname(__DIR__);

return array (
  ...
  // 最后位置添加一行
  'myweishanli/yii2-extjs-rbac' => 
  array (
    'name' => 'myweishanli/yii2-extjs-rbac',
    'version' => '1.0.3.0',
    'alias' => 
    array (
      '@wsl/rbac' => $vendorDir . '/myweishanli/yii2-extjs-rbac',
    ),
  ),
);
```

完成后 [扩展配置](../README.md#2配置)

