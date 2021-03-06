# Laravel Improved Config

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Laravel Version](https://img.shields.io/badge/laravel-5-orange.svg?style=flat-square)](http://laravel.com)

![Laravel Conf](conf.png)

Custom editable configs for Laravel 5.

This package helps you to store your additional configuration in your own files.

This is helpfull when you need to edit your configuration by user from GUI. i.e. Website settings.

Config file will be stored into `storage/app/conf.json`.

## Install

Add

``` JSON
"gaaarfild/laravel-conf": "1.*"
```

to your `composer.json` file into `require` section.

Then type in console

``` BASH
$ composer update
```

When update completed, add to your `config/app.conf` file to `providers` section

``` PHP
'providers' => [
    // ...
    Gaaarfild\LaravelConf\LaravelConfServiceProvider::class,
]
```

If you want to use `Conf` facade, add to same file at the `aliases` section

``` PHP
'aliases' => [
    // ...
  'Conf' => Gaaarfild\LaravelConf\ConfFacade::class,
]
```


## Usage

### Get config value

``` php
Conf::get('key.to.retrieve', 'default_value');
```

You can optionally set the third parameter 'withFallback'.

If no such value in JSON-file, it will try to get it from native config array.

Else will return default value.

Could be used 'dot' notation

### Save config value

``` PHP
Conf::set('key', 'value_to_save');
```

Could be used 'dot' notation

### Removing key from config

``` PHP
Conf::forget('key');
```

Could be used 'dot' notation

### Get entire config

``` PHP
Conf::all();
```

### Check config key existence

``` PHP
Conf::has('key.to.check', true);
```

Second parameter `withFallback`.

If true, it also checks for native laravel config key existence.

Could be used 'dot' notation

## Contributions

Contributions are highly appreciated.

Send your pull requests to `master` branch.


## License

The MIT License (MIT). Please see [License File](https://github.com/gaaarfild/laravel-conf/blob/master/LICENSE) for more information.

