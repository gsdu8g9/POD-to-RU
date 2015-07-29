[![Build Status](https://travis-ci.org/mishin/POD-to-RU.svg?branch=master)](https://travis-ci.org/mishin/POD-to-RU)
[![Coverage Status](https://coveralls.io/repos/mishin/POD-to-RU/badge.png?branch=master)](https://coveralls.io/r/mishin/POD-to-RU?branch=master)
[![Kwalitee status](http://cpants.cpanauthors.org/dist/POD2-RU.png)](http://cpants.charsbar.org/dist/overview/POD2-RU)
[![GitHub issues](https://img.shields.io/github/issues/mishin/POD-to-RU.svg)](https://github.com/mishin/POD-to-RU/issues)
[![Cpan license](https://img.shields.io/cpan/l/POD2-RU.svg)](https://metacpan.org/release/POD2-RU)
[![Cpan version](https://img.shields.io/cpan/v/POD2-RU.svg)](https://metacpan.org/release/POD2-RU)

# NAME

POD2::RU - Документация Perl по-русски

# SYNOPSIS

    use POD2::RU;
    print_pods();
    print_pod('perlre', 'perlootut');

# DESCRIPTION

POD2::RU - проект перевода Perl-документации на русский язык.

# REPOSITORY

Домашняя страница проекта ─ [https://github.com/mishin/POD-to-RU](https://github.com/mishin/POD-to-RU). 

# USAGE

Примеры использования

    perldoc POD2::RU::perlretut

    perl -MPOD2::RU -e 'print_pods'
    perl -MPOD2::RU -e 'print_pod <название_pod1> [<название_pod2> ...]'

    use POD2::RU;
    print_pods();
    print_pod('pod_foo', 'pod_baz');

После установки пакета, вы можете использовать следующую команду, чтобы получить документацию:

    perldoc POD2::RU::<название_pod>

Начиная с Pod::Perldoc версии 3.14 можно использовать следующий синтаксис:

    perldoc -L RU <название_pod>
    perldoc -L RU -f <функция>
    perldoc -L RU -q <регулярное выражение для FAQ>

Модификатор  `-L` определяет код языка перевода. Если пакет `POD2::<код_языка>` не существует, то модификатор игнорируется.

Для ленивых можно добавить псевдоним (alias):

    perldoc-ru="perldoc -L RU"

для того, чтобы не писать модификатор  `-L` каждый раз:

    perldoc-ru perlre
    perldoc-ru -f map

Начиная с  `Pod::Perldoc` версии 3.15 вы можете использовать переменную среды PERLDOC\_POD2. Если эта переменная установлена в '1', то perldoc осуществляет поиск pod документации на языке, указанном в переменной LC\_ALL, LANG или LC\_LANG. Или же вы можете установить значение "ru", означающее вывод документации на русском языке. Например,

       export PERLDOC_POD2="ru"
       perldoc perl

# API

Пакет экспортирует следующие функции:

- `new`

    Была добавлена для совместимости с `perldoc` Perl 5.10.1.
    [Pod::Perldoc](https://metacpan.org/pod/Pod::Perldoc) использует ее для возврата имени пакета перевода.

- `pod_dirs`

    Была добавлена для совместимости с `perldoc` Perl 5.10.1.
    [Pod::Perldoc](https://metacpan.org/pod/Pod::Perldoc) использует ее для определения, где искать переведенные файлы.

- `print_pods`

    Выводит все переведенные части и оригинальную версию Perl.

- `print_pod`

    Выводит на экран оригинальнуя версию Perl для всех частей, переданых в качестве аргументов.

- `search_perlfunc_re`

    `perldoc -f function` использует возвращаемое значение этой функции (как regexp), чтобы пропустить введение и найти список функций.

- `pod_info`

    `<pod_info`> - Выдает хэш с текущими pod файлами в данном дистрибутиве

# AUTHOR

Nikolay Mishin < mi@ya.ru >

# CONTRIBUTORS

- Анатолий Шарифулин ([SHARIFULN](https://metacpan.org/author/SHARIFULN))
- Андрей Шитов ([ANDY](https://metacpan.org/author/ANDY))
- Алексей Суриков ([KSURI](https://metacpan.org/author/KSURI))
- Михаил Любимов ([mikhail.lyubimov](http://event.perlrussia.ru/rpw2008/user/4579))
- Дмитрий Константинов ([Dim\_K](http://www.weblancer.net/users/Dim_K/portfolio/))
- Евгений Баранов ([Baranov](http://event.yapcrussia.org/mayperl2/user/161))
- Антон Никишаев ([llelf](https://github.com/llelf))
- Динар Жамалиев ([zhdinar](http://blog.perl5doc.ru))
- Валерий Кравчук ([valera@openxs.kiev.ua](http://www.opennet.ru/search.shtml?exclude=index|%2Fman.shtml&words=valera%40openxs.kiev.ua))
- Enrique Nell ([ENELL](https://metacpan.org/author/ENELL)) 
- Yusuke Kawasaki ([KAWASAKI](https://metacpan.org/author/KAWASAKI))
- Вячеслав Тихановский ([VTI](https://metacpan.org/author/VTI))
- Zoffix Znet ([ZOFFIX](https://metacpan.org/author/ZOFFIX))
- Дмитрий Анисимов
- Андрей Варлашкин
- Кирилл Флоренский
- Андрей Асякин ([asan999](https://metacpan.org/pod/asan999&#x20;at&#x20;gmail.com))

# COPYRIGHT

Copyright 2015- Nikolay Mishin

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# REPOSITORY

[https://github.com/mishin/POD-to-RU](https://github.com/mishin/POD-to-RU)

# SUPPORT

This module is managed in an open [GitHub
repository](http://github.com/mishin/POD-to-RU/). Feel free to fork and
contribute, or to clone [git://github.com/mishin/POD-to-RU.git](git://github.com/mishin/POD-to-RU.git) and send
patches!

Found a bug? Please [post](http://github.com/perl-pod/test-pod/issues) a report!

# SEE ALSO

[POD2::ES](https://metacpan.org/pod/POD2::ES), [POD2::PT\_BR](https://metacpan.org/pod/POD2::PT_BR), [POD2::IT](https://metacpan.org/pod/POD2::IT), [POD2::FR](https://metacpan.org/pod/POD2::FR), [POD2::LT](https://metacpan.org/pod/POD2::LT).

# DONATIONS

Проект перевода документации Perl требует постоянных усилий, что доступно только для сильных духом и альтруистов.
Авторы не просят, но ни не отвергают помощь в виде денег, книг, сыра и продуктов из свинины (можно хамон;) ), или даже поездки в Полинезию для снижения утомления и сохранения боевого духа команды. Мы приглашаем всех. (стащено и переведено отсюда [POD2::ES](https://metacpan.org/pod/POD2::ES))

# THANKS 

Авторы хотели бы выразить свою благодарность команде разработчиков OmegaT, инструмента, который используется для перевода.

Проект OmegaT: [http://omegat.org/](http://omegat.org/)

Также хотелось бы выразить благодарность автору перевода perl документации на испанский язык 
POD2::ES Enrique Nell за его в помощь в написании скриптов.

Проект POD2::ES: [https://github.com/zipf/perldoc-es](https://github.com/zipf/perldoc-es)

Благодарность Yusuke Kawasaki за совет разместить весь проект на github
на вопрос о японской документации он ответил:
They (JPRP people) uses sourceforge and its CVS. 

[http://sourceforge.jp/cvs/view/perldocjp/docs/modules/](http://sourceforge.jp/cvs/view/perldocjp/docs/modules/)

They are using a traditional mailing list and sourceforge's bug tracking system. In my opinion, github would be a much better way to manage those things at the moment. github was not exist when they started the project.

Спасибо Яндекс Спеллеру [https://tech.yandex.ru/speller/](https://tech.yandex.ru/speller/), [http://speller.yandex.net/speller/1.0/index.html](http://speller.yandex.net/speller/1.0/index.html) за то, что через него можно прогнать русский
текст и удобно исправить ошибки!

Спасибо сайту [http://online.orfo.ru/](http://online.orfo.ru/) - он выручал даже тогда, когда был бессилен Яндекс Спеллер.

Спасибо переводчику [http://www.bing.com/translator/](http://www.bing.com/translator/) за хороший предварительный перевод,
но помучаться все равно придется, получается пока сыро;)

Спасибо [Mail.ru](https://metacpan.org/pod/Mail.ru) за проведение конференции YAPC Russia 2015 
и лично Павлу Щербинину.
