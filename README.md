# Recaptcha Plugin for CakePHP #

This plugin is cloned from CakeDC's recaptcha plugin with a different versioning schema to support legacy Cake apps using Recaptcha v2 & v3. See [the original project](https://github.com/CakeDC/recaptcha) for docs. Tests and locales are not currently being used.

The versioning system for this project is as follows:
1. Each version of Cake with a supported version has that version in its own branch (i.e. the plugin for CakePHP v2.3 is on branch 2.3.x)

The following comes from the original readme:

## Usage ##

To use the recaptcha plugin its required to include the following two lines in your `/app/Config/bootstrap.php` file.

	Configure::write('Recaptcha.publicKey', 'your-public-api-key');
	Configure::write('Recaptcha.privateKey', 'your-private-api-key');

Don't forget to replace the placeholder text with your actual keys!

Keys can be obtained for free from the [Recaptcha website](http://www.google.com/recaptcha).

Controllers that will be using recaptcha require the Recaptcha Component to be included. Through inclusion of the component, the helper is automatically made available to your views.

In the view simply call the helpers `display()` method to render the recaptcha input:

	echo $this->Recaptcha->display();

You could select another theme, setup it as parameter, for istance:

	echo $this->Recaptcha->display(array('recaptchaOptions'=>array('theme' => 'blackglass')));

For the complete list of themes, take a look here: [http://code.google.com/intl/it-IT/apis/recaptcha/docs/customization.html](http://code.google.com/intl/it-IT/apis/recaptcha/docs/customization.html).

To check the result simply do something like this in your controller:

	if ($this->request->is('post')) {
		if ($this->Recaptcha->verify()) {
			// do something, save you data, login, whatever
		} else {
			// display the raw API error
			$this->Session->setFlash($this->Recaptcha->error);
		}
	}

## Requirements ##

* PHP version: PHP 5.2+

## Support ##

For support and feature request, please visit the [Recaptcha Plugin Support Site](https://github.com/CakeDC/recaptcha/issues).

For more information about our Professional CakePHP Services please visit the [Cake Development Corporation website](http://cakedc.com).

## License ##

Copyright 2009-2014, [Cake Development Corporation](http://cakedc.com)

Licensed under [The MIT License](http://www.opensource.org/licenses/mit-license.php)<br/>
Redistributions of files must retain the above copyright notice.

## Copyright ###

Copyright 2009-2011<br/>
[Cake Development Corporation](http://cakedc.com)<br/>
1785 E. Sahara Avenue, Suite 490-423<br/>
Las Vegas, Nevada 89104<br/>
http://cakedc.com<br/>
