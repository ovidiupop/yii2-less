Yii2 Less.php
=============
This is a Yii2 wrapper extension for PHP port of the official LESS processor http://lesscss.org

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require --prefer-dist ovidiupop/yii2-less "~1.0"

```

or add

```
"ovidiupop/yii2-less": "~1.0"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your config:

```php
$config = [
    'components' => [
        'assetManager' => [
            'converter' => [
                'class' => 'ovidiupop\lessphp\AssetConverter',
                'force'=> true,     // Optional: On true will convert all .less files. You can make all changes in variable.less
                'compress' => true, // Optional: You can tell less.php to remove comments and whitespace to generate minimized css files.
                'useCache' => true, // Optional: less.php will save serialized parser data for each .less file. Faster, but more memory-intense.
                //'cacheDir' => null, // Optional: is passed to the SetCacheDir() method.
                'cacheSuffix' => true, // Optional: Filename suffix to avoid the browser cache and force recompiling by configuration changes
            ],
        ],
    ],
];
```

Now you can specify your less files in asset bundle:

```php
class AppAsset extends AssetBundle
{
    public $basePath = '@webroot';
    public $baseUrl = '@web';
    public $css = [
        'css/site.less',
    ];
    public $js = [
    ];
    public $depends = [
    ];
}
```
