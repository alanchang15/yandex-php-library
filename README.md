PHP Yandex API
============================

## 安裝

### 版本

В библиотеке для отправки запросов к API используется Guzzle. Причем следует иметь в виду что вплоть до 0.4.1 
включительно использовался [Guzzle 3](https://github.com/guzzle/guzzle3) и соответственно поддерживался php 5.3.

Позже был сделан переход к php 5.4 и [Guzzle 5](https://github.com/guzzle/guzzle/tree/5.3). Эта версия php и Guzzle 
поддерживаются в версиях библиотеки > 0.4.1 и < 2.0.0 (из стабильных релизов это 1.0.0).
Выпуск обновлений для этой версии под вопросом.

В 2.0.0 был сделан переход к php 5.5 и [Guzzle 6](https://github.com/guzzle/guzzle). Это последняя версия которая будет поддерживать php 5.5. Если ваше приложение работает на php 5.5 ограничьте версию в composer.json 2й версией (например так "~2.0")

В версии 3.0.0 будет убрана поддержка php 5.5. 

### composer

Установка с использованием менеджера пакетов [Composer](http://getcomposer.org):

```bash
$ curl -s https://getcomposer.org/installer | php
```

Теперь вносим изменения в ваш `composer.json`:

```yaml
{
    "require": {
        "nixsolutions/yandex-php-library": "dev-master"
    }
}
```

### phar-архив

Работа с [phar архивом](http://php.net/manual/en/book.phar.php):

1. Скачиваем по [ссылке](http://yadi.sk/d/26YmC3hRByBd7) phar-файл или bz2-архив с ним, последней или конкретной версии.
2. Сохраняем в папку с проектом.
3. Используем!

Пример подключения и работа с библиотекой из phar-архива:
```php
<?php
//Подключаем autoload.php из phar-архива
require_once 'phar://yandex-php-library_master.phar/vendor/autoload.php';

use Yandex\Disk\DiskClient;

$disk = new DiskClient();
//Устанавливаем полученный токен
$disk->setAccessToken(TOKEN);

//Получаем список файлов из директории
$files = $disk->directoryContents();
```

## Использование

* [Yandex Disk](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Disk)
* [Yandex Market for Partner](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Market-for-Partner)
* [Yandex Market Content](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Market-Content)
* [Yandex OAuth](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-OAuth)
* [Yandex Site Search Pinger](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Site-Search-Pinger)
* [Yandex Safe Browsing](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Safe-Browsing)
* [Yandex Metrica](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Metrica)
* [Yandex Dictionary](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Dictionary)
* [Yandex Speller](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-Speller)
* [Yandex DataSync](https://github.com/nixsolutions/yandex-php-library/wiki/Yandex-DataSync)

## Лицензия

Пакет `yandex-php-library` распространяется под лицензией MIT (текст лицензии вы найдёте в файле
[LICENSE](https://raw.github.com/nixsolutions/yandex-php-library/master/LICENSE)), данная лицензия
распространяется на код данной библиотеки и только на неё, использование сервисов Яндекс регулируются
документами, которые вы сможете найти на странице [Правовые документы](http://legal.yandex.ru/)
