## Use Laravel UI with Fortify

## Install Laravel
`laravel new fortify-ui-app  `

### Install Laravel UI
`composer require laravel/ui`  
`php artisan ui bootstrap --auth`  
`npm install && npm run dev`    
`php artisan migrate`

### Installation fortify
`composer require laravel/fortify`  
`php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"`  
`php artisan migrate`

## config

> add this line in app/config.php

`App\Providers\FortifyServiceProvider::class,`

**Delete folder app/Http/Controllers/Auth**  
> Edit Providers/FortifyServiceProvider.php in boot function

```
Fortify::loginView(function () {
            return view('auth.login');
        });  

Fortify::registerView(function () {
            return view('auth.register');
        }); 

Fortify::requestPasswordResetLinkView(function () {
            return view('auth.passwords.email');
        }); 
```  
## Add GDPR Cookie Consent in Laravel

> using a package by spatie  

`composer require spatie/laravel-cookie-consent`

> Publish the config, and view files:  

`php artisan vendor:publish --provider="Spatie\CookieConsent\CookieConsentServiceProvider" --tag="cookie-consent-config"`

`php artisan vendor:publish --provider="Spatie\CookieConsent\CookieConsentServiceProvider" --tag="cookie-consent-views"`

> Now, the package is all set, you can simply put the following line of code within your body tags to make it work, likeso:

```
//in your blade template
@include('cookie-consent::index')
```




