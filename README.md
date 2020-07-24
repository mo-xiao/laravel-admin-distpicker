纬度和经度选择器
======

这个扩展用来帮助你在form表单中选择经纬度，用来替代`Laravel-admin`中内置的`Form\Field\Map`组件, 组件支持的地图包括`Google map`、`百度地图`、`高德地图`、`腾讯地图`、`Yadex map`.

此扩展名用于帮助您选择表单中的纬度和经度，该纬度和经度用于替换  `Laravel-admin` 内置 `Form\Field\Map` 组件。支持的地图包括 `Google map`, `Baidu map`, `AMap`, `Tencent Map`, `Yadex map`.

## 安装

```bash
composer require laravel-admin-ext/latlong -vvv
```

## 组态

打开`config/admin.php`并将以下配置添加到扩展部分:

```php

    'extensions' => [

        'latlong' => [

            //是否启用此扩展，默认为true'enable 
            'enable' => true,

            //指定默认提供程序
            'default' => 'google',

            //根据上面选择的提供者，填写相应的api_key'providers 
            'providers' => [

                'google' => [
                    'api_key' => '',
                ],
                
                'yadex' => [
                    'api_key' => '',
                ],

                'baidu' => [
                    'api_key' => 'xck5u2lga9n1bZkiaXIHtMufWXQnVhdx',
                ],

                'tencent' => [
                    'api_key' => 'VVYBZ-HRJCX-NOJ4Z-ZO3PU-ZZA2J-QPBBT',
                ],

                'amap' => [
                    'api_key' => '3693fe745aea0df8852739dac08a22fb',
                ],
            ]
        ]
    ]

```

## 用法

假设你有两个字段 latitude ，并 longitude 在表中表示纬度和经度，然后使用形式如下
```php
$form->latlong('latitude', 'longitude', 'Position');

//设置地图高度
$form->latlong('latitude', 'longitude', 'Position')->height(500);

//设置地图缩放
$form->latlong('latitude', 'longitude', 'Position')->zoom(16);

//设置默认位置
$form->latlong('latitude', 'longitude', 'Position')->default(['lat' => 90, 'lng' => 90]);
```

在显示页面中使用

```php
$show->field('Position')->latlong('lat_column', 'long_column', $height = 400, $zoom = 16);
```

## 打赏

如果觉得这个项目帮你节约了时间，不妨支持一下;)

![-1](https://img-blog.csdnimg.cn/2020072411290773.png)

