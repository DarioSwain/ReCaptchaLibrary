Google ReCAPTCHA ver.2 backend provider
================================================

You can find full documentation about Google reCAPTCHA API v2 [here](http://developers.google.com/recaptcha/intro).

Installation
------------

You can install this package with [Composer](http://getcomposer.org/).
Add next lines to your composer.json file:

``` json
{
    "require": {
        "dario_swain/ds-recaptcha-library": "dev-master"
    }
}
```

Usage Example
-------------

Use ReCaptcha class for sending request to google API:

``` php
<?php

    $privateKey = 'PRIVATE_KEY'; //You Google API private key
    $clientIp = $_SERVER['REMOTE_ADDR']; //Client IP Address
    $gReCaptchaResponse = $_POST['g-recaptcha-response']; //Google reCAPTCHA response

    $reCaptcha = new ReCaptcha($privateKey, $clientIp, $gReCaptchaResponse);
	$response = $reCaptcha->buildRequest()->send();

	if($response->isSuccess())
    {
        //Submit form ...
    }

```

Copyright
---------

Copyright (c) 2015 Ilya Pokamestov <dario_swain@yahoo.com>.