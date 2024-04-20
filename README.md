# Лабораторная работа: Создание Docker-контейнера с веб-приложением

## Описание

Данный проект содержит инструкции и файлы для создания Docker-контейнера, внутри которого развернуто веб-приложение WordPress, работающее на сервере Apache с базой данных MariaDB.

## Цель

Целью данной лабораторной работы является ознакомление с процессом создания и настройки Docker-контейнера для веб-приложения, а также управления его компонентами.

## Инструкции

### Задание

1. Создать Docker-контейнер с веб-приложением, включающим в себя сервер Apache, интерпретатор PHP и базу данных MariaDB.
2. Настроить контейнер для запуска WordPress.
3. Создать отчет с пошаговым описанием выполнения проекта.

### Выполнение

1. **Настройка конфигурационных файлов:**

   - Apache2:
     - 000-default.conf
     - apache2.conf
   - PHP:
     - php.ini
   - MariaDB:
     - 50-server.cnf
   - Supervisor:
     - supervisord.conf

2. **Ответы на вопросы:**

- За что отвечает инструкция DirectoryIndex в файле конфигурации apache2?
  Инструкция DirectoryIndex в файле конфигурации Apache2 определяет порядок приоритета индексных файлов при обращении к директориям сервером. Например, если в директории нет файла, указанного первым в DirectoryIndex, сервер будет искать следующий файл в списке.

- Зачем нужен файл wp-config.php?
  Файл wp-config.php - это конфигурационный файл для WordPress. Он содержит настройки подключения к базе данных, а также другие параметры, необходимые для работы приложения.

- За что отвечает параметр post_max_size в файле конфигурации php?
  Параметр post_max_size в файле конфигурации PHP определяет максимальный размер данных, который может быть передан в POST-запросе. Этот параметр ограничивает размер POST-данных, отправляемых на сервер.

- Укажите, на ваш взгляд, какие недостатки есть в созданном образе контейнера?
  Недостатки созданного образа контейнера могут включать:
  Отсутствие управления версиями внешних зависимостей (например, версии WordPress, PHP и MariaDB зафиксированы только в момент сборки контейнера).
  Ограниченная настройка безопасности (например, отсутствие настроек аутентификации для базы данных).
  Неэффективное использование ресурсов (например, не оптимизированные образы или не минимизированные слои контейнера).

## Выводы

В ходе работы был успешно создан Docker-контейнер с веб-приложением WordPress, настроены конфигурационные файлы для каждого компонента, а также создана конфигурация Supervisor для управления процессами в контейнере. Работоспособность приложения была успешно проверена.
