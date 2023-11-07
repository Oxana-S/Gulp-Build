# Сборка проекта на Gulp 4

Данная сборка форкнута с github: https://github.com/morphIsmail/testGulpBuild и переработана мной.

Задача:
Быстро настроить сборку проекта на Gulp и писать код на:

- HTML
- CSS, SCSS, SASS
- Java Script

## Функционал сборки

HTML

- минификация HTML, только в режиме production
- добавление блоков html файлов в главный - index.html

SCSS, CSS

- компиляция препроцессоров SASS, SCSS
- минификация CSS, только в режиме production
- автоматическое добавление префиксов CSS

JS

- преобразования кода ECMAScript 2015 + в обратно совместимую версию JavaScript с помощью Babel
- минификация JavaScript, только в режиме production
- объединение нескольких файлов JavaScript в один

IMG

- сжатие изображений
- отслеживание новых изображений, которые еще не были сжаты
- отслеживание изменений в файлах и автоматический запуск повторной обработки

SCSS, JS

- генерация sourcemaps

HTML, SCSS, CSS, JS, IMG

- отображение размеров файлов в терминале
- локальный сервер с автоматическим обновлением страницы при изменении файлов.  
  Много промучился у себя на компьютере, сервер то перезагружал страницу, то нет.

## Input

|                |                       HTML                        |            Styles            |            Scripts             |      Images      |
| :------------- | :-----------------------------------------------: | :--------------------------: | :----------------------------: | :--------------: |
| **Каталог**    | src/, src/partials/dev/, src/partials/production/ | src/styles/, src/styles/lib/ | src/scripts/, src/scripts/lib/ |     src/img/     |
| **Расширение** |                       .html                       |         .css, .scss          |              .js               | .jpg, .png, .gif |

## Output

|          | HTML  |          CSS           |     JavaScript      |  Images   |
| :------- | :---: | :--------------------: | :-----------------: | :-------: |
| **Путь** | dist/ | dist/css/style.min.css | dist/js/main.min.js | dist/img/ |

## Зупуск:

1. Скачать все файлы проекта:

   > package.json  
   > gulpfile.js  
   > README.md  
   > .gitignore

2. В терминале перейти в каталог проекта
3. Выполнить команду:
   > npm i (должен быть установлен node.js)
4. Создать каталоги и файлы в папке

   > 'src'

5. Выполнить команду в режиме разработки (dev): _gulp_ (запуск таска default).  
   Подключается в index.html плагином gulp-file-include файл '_src/dev/partials/browsersync_reload.html_' (в нем находится скрипт для запуска _browsersync_.  
   Сделал этот костыль, потомучто _browsersync_ то обновляет страницу, то нет) для 100% работы плагина _browsersync_ по перезагрузке страницы при сохранении изменений в ходе редактирования файлов проекта.
6. Выполнить команду в режиме продакшн (production): _gulp --production_ (запуск таска для продакшн).  
   В этом режиме подключается в index.html плагином gulp-file-include файл 'src/production/partials/browsersync*reload.html' с пустым содержимым, и скрипт для запуска \_browsersync* **не подключается**.

7. Писать свой код и наслаждаться автоматической сборкой проекта.
8. Внимание! Не закомментировать ничего в файле package.json

## Используемые NPM пакеты

[gulp](https://www.npmjs.com/package/gulp) Сборщик Gulp  
[gulp-htmlmin](https://www.npmjs.com/package/gulp-htmlmin) Минификация HTML файлов  
[sass](https://www.npmjs.com/package/sass) Компилятор Sass  
[gulp-sass](https://www.npmjs.com/package/gulp-sass) Компиляция Sass и Scss файлов  
[gulp-uglify](https://www.npmjs.com/package/gulp-uglify) Сжатие и оптимизация Java Script кода  
[gulp-babel](https://www.npmjs.com/package/gulp-babel) Преобразует Java Script в старый стандарт  
[@babel/core](https://www.npmjs.com/package/@babel/core) Ядро Babel  
[@babel/preset-env](https://www.npmjs.com/package/@babel/preset-env) Пресет для компиляции Babel  
[gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css) Минификация и оптимизация CSS файлов  
[del](https://www.npmjs.com/package/del) Удаление каталогов и файлов  
[gulp-sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps) Карта строк кода для инструментов разработчика  
[gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer) Автоматическое добавление префиксов в CSS  
[gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin) Сжатие изображений  
[gulp-concat](https://www.npmjs.com/package/gulp-concat) Объединение нескольких файлов в один  
[gulp-newer](https://www.npmjs.com/package/gulp-newer) Отслеживание только новых файлов  
[gulp-rename](https://www.npmjs.com/package/gulp-rename) Переименовывает файлы  
[gulp-size](https://www.npmjs.com/package/gulp-size) Отображение информации о размерах файлов в терминале  
[browser-sync](https://browsersync.io/docs/gulp) Автоматическое обновление сайта при изменении файлов
[yargs](https://github.com/yargs/yargs) Yargs помогает создавать интерактивные инструменты командной строки, анализируя аргументы. Например запускать gulp с аргументом --production
[gulp-if](https://github.com/robrich/gulp-if) условное управление потоком

### Автору на кофе

![Сбер VISA](https://img.shields.io/badge/Card-4274320032331582-333?style=for-the-badge&logo=visa&labelColor=08a652)
[![Yoomoney](https://img.shields.io/badge/-Yoomoney-7f2bfd?style=for-the-badge)](https://yasobe.ru/na/)
[![PayPal](https://img.shields.io/badge/-PayPal-0070ba?style=for-the-badge&logo=PayPal&logoColor=FF0000)](https://paypal.me/)

### Контакты

[![YouTube](https://img.shields.io/badge/-YouTube-333?style=for-the-badge&logo=YouTube&logoColor=FF0000)](https://www.youtube.com/)
[![Telegram](https://img.shields.io/badge/-Telegram-333?style=for-the-badge&logo=telegram&logoColor=27A0D9)](https://t.me/)
[![VK](https://img.shields.io/badge/-VK-333?style=for-the-badge&logo=Vk&logoColor=27A0D9)](https://vk.com/)
[![GitHub](https://img.shields.io/badge/-GitHub-333?style=for-the-badge&logo=GitHub&logoColor=fff)](https://github.com/)
