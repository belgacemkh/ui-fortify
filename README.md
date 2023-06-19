##

### Install Laravel UI
composer require laravel/ui

php artisan ui bootstrap --auth
npm install && npm run dev

php artisan migrate
### Installation fortify

'composer require laravel/fortify'
php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"


php artisan migrate


## config

app/config.php

App\Providers\FortifyServiceProvider::class,

Providers/FortifyServiceProvider.php in boot function

Fortify::loginView(function () {
            return view('auth.login');
        });  

        Fortify::registerView(function () {
            return view('auth.register');
        }); 

        Fortify::requestPasswordResetLinkView(function () {
            return view('auth.passwords.email');
        }); 

