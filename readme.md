<p align="center"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></p>

<p align="center">
    
##Introduction:

i am use milon/barcode package for generating barcode in laravel application. We generate barcode in HTML, but you can also generate code in png embedded base64 code or SVG canvas as per your requirement. There are two major barcode types.

    1.One-Dimensional (1D) Barcode Types
    2.Two-Dimensional (2D) Barcode Types
 
##User Guide:##
#1: Download Laravel Project

Establish  Laravel Project by the typing following command:

composer create-project --prefer-dist laravel/laravel barcodegenerator

#2: Install milon/barcode Package

First, install milon/barcode package via the Composer package manager:

composer require milon/barcode

Let’s Add BarcodeServiceProvider in config/app.php:

'providers' => [
    ...
    Milon\Barcode\BarcodeServiceProvider::class,
    ...
]

And finally, add in the alias section config/app.php

'aliases' => [
    ...
    'DNS1D' => Milon\Barcode\Facades\DNS1DFacade::class,
    'DNS2D' => Milon\Barcode\Facades\DNS2DFacade::class,
]

#3: Create a Controller:

php artisan make:controller BarcodegeneratorController


It will build a controller file called BarcodegeneratorController.php.

Create a barcode() function in BarcodegeneratorController.


##BarcodegeneratorController.php


barcode() function return view called barcodegenerator which we create shortly.

#4: Define Route:

We register all route in a web.php file.

web.php

Route::get('/barcode','BarcodegeneratorController@barcode');

#5: Create a View File:

Create a file in resources/ views/barcodegenerator.blade.php and put this following code in it.

barcodegenerator.blade.php 



Here we can add One-Dimensional(1D) barcode types.

##Next, we can add Two-Dimensional(2D)barcode types. We can add 2D barcode types like ‘QRCODE’,’PDF417′,’DATAMATRIX’.

barcodegenerator.blade.php



Thank You.

## Contributing:

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).
