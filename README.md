
**laravel 11版本**


### 环境
 - PHP >= 8.2.0
 - Laravel 11.*
 - Fileinfo PHP Extension

### 安装

首先需要安装`laravel`框架，如已安装可以跳过此步骤。如果您是第一次使用`laravel`，请务必先阅读文档 [安装 《Laravel中文文档》](https://learnku.com/docs/laravel/8.x/installation/9354) ！
```bash
composer create-project --prefer-dist laravel/laravel 项目名称 11.*

安装完`laravel`之后需要修改`.env`文件，设置数据库连接设置正确

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=dcat-admin
DB_USERNAME=root
DB_PASSWORD=
```

安装`dcat-admin`


```
cd {项目名称}
git clone https://github.com/icuy/dcat-admin.git ./vendor/dcat/laravel-admin
composer install
composer require dcat/laravel-admin
```

然后运行下面的命令来发布资源：

```
php artisan admin:publish
```


在该命令会生成配置文件`config/admin.php`，可以在里面修改安装的地址、数据库连接、以及表名，建议都是用默认配置不修改。

然后运行下面的命令完成安装：

> 执行这一步命令可能会报以下错误`Specified key was too long ... 767 bytes`，如果出现这个报错，请在`app/Providers/AppServiceProvider.php`文件的`boot`方法中加上代码`\Schema::defaultStringLength(191);`，然后删除掉数据库中的所有数据表，再重新运行一遍`php artisan admin:install`命令即可。

```
php artisan admin:install
```

上述步骤操作完成之后就可以配置`web`服务了，**注意需要把`web`目录指向`public`目录**！如果用的是`nginx`，还需要在配置中加上伪静态配置
```dotenv
location / {
	try_files $uri $uri/ /index.php?$query_string;
}
```

启动服务后，在浏览器打开 `http://localhost/admin`，使用用户名 `admin` 和密码 `admin`登陆。

如果报错**array_merge(): Argument #1 must be of type array, string given**

1、先删除 lang 目录

2、运行 php artisan lang:publish

3、再运行 php artisan admin:publish

<a name="extensions"></a>
### 扩展

| 扩展                                        | 描述                              | dcat-admin 版本                             |
| ------------------------------------------------ | ---------------------------------------- |---------------------------------------- |
| [mosiboom/dcat-iframe-tab](https://github.com/mosiboom/dcat-iframe-tab)    | IFRAME TAB标签切换 | 2.x |
| [super-eggs/dcat-distpicker](https://github.com/super-eggs/dcat-distpicker)    | 省市区联动 | 2.x |
| [ueditor](https://github.com/jqhph/dcat-admin-ueditor) | 百度在线编辑器     | 1.x |
| [grid-sortable](https://github.com/jqhph/dcat-admin-grid-sortable) | 表格拖曳排序工具      | 1.x |


### 鸣谢
`Dcat Admin` 基于以下组件:

+ [Laravel](https://laravel.com/)
+ [Laravel Admin](https://www.laravel-admin.org/)
+ [AdminLTE3](https://github.com/ColorlibHQ/AdminLTE)
+ [bootstrap4](https://getbootstrap.com/)
+ [jQuery3](https://jquery.com/)
+ [Eonasdan Datetimepicker](https://github.com/Eonasdan/bootstrap-datetimepicker/)
+ [font-awesome](http://fontawesome.io)
+ [jquery-form](https://github.com/jquery-form/form)
+ [moment](http://momentjs.com/)
+ [webuploader](http://fex.baidu.com/webuploader/)
+ [jquery-pjax](https://github.com/defunkt/jquery-pjax)
+ [Nestable](http://dbushell.github.io/Nestable/)
+ [toastr](http://codeseven.github.io/toastr/)
+ [editor-md](https://github.com/pandao/editor.md)
+ [fontawesome-iconpicker](https://github.com/itsjavi/fontawesome-iconpicker)
+ [layer弹出层](http://layer.layui.com/)
+ [char.js](https://www.chartjs.org)
+ [nprogress](https://ricostacruz.com/nprogress/)
+ [bootstrap-validator](https://github.com/1000hz/bootstrap-validator)
+ [Google map](https://www.google.com/maps)
+ [Tencent map](http://lbs.qq.com/)

### Contributors

#### Code Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].
<a href="https://github.com/jqhph/dcat-admin/graphs/contributors"><img src="https://opencollective.com/dcat-admin/contributors.svg?width=890&button=false" /></a>

### Financial Contributors

Become a financial contributor and help us sustain our community. [[Contribute](https://opencollective.com/dcat-admin/contribute)]

#### Individuals

<a href="https://opencollective.com/dcat-admin"><img src="https://opencollective.com/dcat-admin/individuals.svg?width=890"></a>

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. [[Contribute](https://opencollective.com/dcat-admin/contribute)]

<a href="https://opencollective.com/dcat-admin/organization/0/website"><img src="https://opencollective.com/dcat-admin/organization/0/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/1/website"><img src="https://opencollective.com/dcat-admin/organization/1/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/2/website"><img src="https://opencollective.com/dcat-admin/organization/2/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/3/website"><img src="https://opencollective.com/dcat-admin/organization/3/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/4/website"><img src="https://opencollective.com/dcat-admin/organization/4/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/5/website"><img src="https://opencollective.com/dcat-admin/organization/5/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/6/website"><img src="https://opencollective.com/dcat-admin/organization/6/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/7/website"><img src="https://opencollective.com/dcat-admin/organization/7/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/8/website"><img src="https://opencollective.com/dcat-admin/organization/8/avatar.svg"></a>
<a href="https://opencollective.com/dcat-admin/organization/9/website"><img src="https://opencollective.com/dcat-admin/organization/9/avatar.svg"></a>

### License
------------
`dcat-admin` is licensed under [The MIT License (MIT)](LICENSE).
