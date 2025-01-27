## This package is based on the repo maintained by hevelius.

# Flysystem adapter for the Microsoft OneDrive API

[![Latest Version on Packagist](https://img.shields.io/packagist/v/hevelius/flysystem-onedrive.svg?style=flat-square)](https://packagist.org/packages/hevelius/flysystem-onedrive)


This package contains a [Flysystem](https://flysystem.thephpleague.com/) adapter for OneDrive. Under the hood, the [Microsoft Graph SDK](https://github.com/microsoftgraph/msgraph-sdk-php) is used.

## Installation

You can install the package via composer:

``` bash
composer require cialtronale/flysystem-onedrive
```
or add direct this repo in composer.json

```json
"repositories": [
        {
            "url": "https://github.com/cialtronale/flysystem-onedrive.git",
            "type": "git"
        }
    ],
```

## Usage

The first thing you need to do is get an authorization token for the Microsoft Graph API. For that you need to create an app on the [Microsoft Azure Portal](https://portal.azure.com/).

``` php
use Microsoft\Graph\Graph;
use League\Flysystem\Filesystem;
use MarioPerrotta\FlysystemOneDrive\OneDriveAdapter;

$graph = new Graph();
$graph->setAccessToken('EwBIA8l6BAAU7p9QDpi...');

$adapter = new OneDriveAdapter($graph, 'root');
$filesystem = new Filesystem($adapter);

// Or to use the approot endpoint:
$adapter = new OneDriveAdapter($graph, 'special/approot');
```


## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

- [Nicolas Beauvais](https://github.com/nicolasbeauvais)
- [Mario Perrotta](https://github.com/hevelius)
- [Marca Alessandro](https://github.com/cialtronale)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
