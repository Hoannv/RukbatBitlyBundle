RukbatBitlyBundle
=================

Symfony2 bundle for the [bitly](http://dev.bitly.com/api.html) API.
This bundle wraps the Falicon/BitlyPHP library (https://github.com/Falicon/BitlyPHP) in a Symfony2 bundle.

**License**

RukbatBitlyBundle is licensed under the GNU GPL v2 - see the `Resources/meta/LICENSE` file for details

Setup
-----

- Using the vendors script

      [RukbatBitlyBundle]
          git=https://github.com/rukbat/RukbatBitlyBundle.git
          target=bundles/Rukbat/BitlyBundle

- Add the Rukbat namespace to autoloader

``` php
<?php
   // app/autoload.php
   $loader->registerNamespaces(array(
    // ...
    'Rukbat' => __DIR__.'/../vendor/bundles',
  ));
```

- Add RukbatBitlyBundle to your application kernel

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Rukbat\BitlyBundle\SOGEnomBundle(),
    );
}
```
- Yml configuration

``` yml
# app/config/config.yml
rukbat_bitly:
    key: yourKey # Required
    login: yourLogin # Required
    clientid: null
    secret: null
```
Visit [http://bitly.com/a/settings/advanced] for more details.

Usage
-----

 - Using service

Open your controller and call the service.

``` php
<?php
    $bitly = $this->get('RukbatBitly');
?>
```