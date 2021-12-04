---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
author: |
	Сидоракин
institute: |
	 RUDN University, Moscow, Russian Federation
date: Ноябрь, 2021 Москва

## Formatting
toc: false
slide_level: 2
theme: metropolis
sansfont: NotoMono-Regular
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---
## Цель лабораторной работы

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1. Проверить работу SELinx на практике совместно с веб-сервером Apache.


## Проверяем, что SELinux работает в режиме enforcing политики targeted.
![getenforce и sestatus](image/1.jpg){ #fig:001 width=40% }

## Убеждаемся, что веб-браузер работает.
![service](image/2.jpg){ #fig:002 width=50% }

## Найходим веб-сервер Apache в списке процессов
![Apache](image/3.jpg){ #fig:003 width=50% }

## Смотрим состояние переключателей SELinux для Apache 
![SELinux](image/4.jpg){ #fig:003 width=50% }

## Определяем тип файлов и поддиректорий, находящихся в директории "/var/www"
![тип файлов](image/6.jpg){ #fig:004 width=50% }

## Cоздаем от имени суперпользователя html-файл "/var/www/html/test.html"
![test.html](image/9.jpg){ #fig:007 width=50% }

## Содержание файла
![test.html](image/9.1.jpg){ #fig:007 width=50% }

## Вводим в браузере адрес "http://127.0.0.1/test.html"
![Браузер](image/11.jpg){ #fig:007 width=50% }

## Изучаем справку man httpd_selinux
![man httpd_selinux](image/12.jpg){ #fig:007 width=50% }

## Изменяем контекст файла "/var/www/html/test.html"
![Контекст файла](image/13.png){ #fig:007 width=50% }


## Попробуем ещё раз получить доступ к файлу 
![simpleid2 и id](image/14.jpg){ #fig:007 width=50% }

## Выполняем перезапуск веб-сервера Apache
![readfile.c](image/17.jpg){ #fig:007 width=50% }


## Выполняем команду "semanage port -a -t http_port_t -р tcp 81"
![semnage port](image/19.jpg){ #fig:007 width=50% }

## Верните контекст httpd_sys_cоntent__t и пробуем получить доступ к файлу через веб-сервер.
![httpd_sys_content_t](image/21.jpg){ #fig:007 width=50% }

## Удаляем файл test.html: rm "/var/www/html/test.html"
![readfile.c](image/24.jpg){ #fig:007 width=50% }





## Вывод
В результате выполнения лабораторной работы мы развили навыки администрирования ОС Linux. Получили первое практическое знакомство с технологией SELinux1. Проверили работу SELinx на практике совместно с веб-сервером Apache.