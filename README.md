# TimeBundle
Provides a simple twig filter for expressing time difference in words for Symfony. 
Uses a range of +-7 days, after that, the actual date is returned.

## Install
composer require /time-ago-bundle ~v0.3
```

app/Appkernel.php:
```php
new Time\TimeAgoBundle\TimeTimeAgoBundle(),
```

## Usage
```php
$now = new \DateTime();

$foo = new \DateTime();
$foo->modify('-3 minutes');

$bar = new \DateTime();
$bar->modify('-3 months');

$foobar = new \DateTime();
$foobar->modify('+4 hours');
```

```twig
{{ now|ago }}
{# just now #}

{{ foo|ago }}
{# 3 minutes ago #}

{{ bar|ago('r') }}
{# actual date in 'r' format #}

{{ foobar|ago }}
{# in 4 hours #}
```

Change [default format](http://php.net/manual/en/function.date.php) in `config.yml`:

```yml
_time_ago:
    format: 'Y-m-d H:i:s'
```

