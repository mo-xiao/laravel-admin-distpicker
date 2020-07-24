纬度和经度选择器
======

这个扩展用来帮助你在form表单中选择经纬度，用来替代`Laravel-admin`中内置的`Form\Field\Map`组件, 组件支持的地图包括`Google map`、`百度地图`、`高德地图`、`腾讯地图`、`Yadex map`.

此扩展名用于帮助您选择表单中的纬度和经度，该纬度和经度用于替换  `Laravel-admin` 内置 `Form\Field\Map` 组件。支持的地图包括 `Google map`, `Baidu map`, `AMap`, `Tencent Map`, `Yadex map`.

## 预览截图

![-1](https://user-images.githubusercontent.com/1479100/45096011-186c8580-b152-11e8-8a38-dcd94cd46d4b.png)

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

## 表单中使用

设置默认值
```php
$form->distpicker([
    'province_id' => '省份',
    'city_id' => '市',
    'district_id' => '区'
], '地域选择')->default([
    'province' => 130000,
    'city'     => 130200,
    'district' => 130203,
]);
```
设置label
```php
$form->distpicker(['province_id', 'city_id', 'district_id'], '请选择区域');
```

表格筛选中使用

```php
$filter->distpicker('province_id', 'city_id', 'district_id', '地域选择');
```

## 打赏

如果觉得这个项目帮你节约了时间，不妨支持一下;)

![-1](https://img-blog.csdnimg.cn/2020072411290773.png)

