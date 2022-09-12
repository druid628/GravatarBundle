Pyrrah/GravatarBundle 🤳
========================

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE)
[![Total Contributors][ico-contributors]][link-contributors]
[![Total Downloads][ico-downloads]][link-downloads]

This bundle allows you to display your avatar anywhere on your site, via the Gravatar service.

Requirements
------------

* Symfony 3.4 to 6
* A [Gravatar account](https://fr.gravatar.com/site/signup) - it's free!

Installation
------------

  1. To install this bundle, run the following [Composer](https://getcomposer.org/) command :

  ```
  composer require pyrrah/gravatar-bundle
  ```

  2. If you always have some default for your gravatars such as size, rating or default it can be configured in your config :

  ```yaml
  # config/packages/pyrrah_gravatar.yaml
  pyrrah_gravatar:
    rating: g
    size: 150
    default: mm
    secure: true
  ```

Usage
-----

All you have to do is use the helper like this example:

```html
<img src="<?php echo $view['gravatar']->getUrl('alias@domain.tld') ?>" />
```

Or with parameters:

```html
<img src="<?php echo $view['gravatar']->getUrl('alias@domain.tld', '80', 'g', 'defaultimage.png', true) ?>" />
```

The only required parameter is the email adress. The rest have default values.

If you use twig you can use the helper like this example:

```
<img src="{{ gravatar('alias@domain.tld') }}" />
```

Or if you want to check if a gravatar email exists:

```
{% if gravatar_exists('alias@domain.tld') %}
  The email is an gravatar email
{% endif %}
```

Or with parameters:

```
<img src="{{ gravatar('alias@domain.tld', size, rating, default, secure) }}" />
```

For more information [look at the gravatar implementation pages][link-gravatar].

Credits
-------

- [Pierre-Yves Dick][link-author]
- [All Contributors][link-contributors]

License
-------

The MIT License (MIT). Please see [License File](LICENSE) for more information.

[ico-version]: https://img.shields.io/packagist/v/pyrrah/gravatar-bundle.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-contributors]: https://img.shields.io/github/contributors/Pyrrah/GravatarBundle?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/pyrrah/gravatar-bundle.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/pyrrah/gravatar-bundle
[link-downloads]: https://packagist.org/packages/pyrrah/gravatar-bundle
[link-author]: https://github.com/Pyrrah
[link-contributors]: ../../contributors
[link-gravatar]: http://en.gravatar.com/site/implement/
