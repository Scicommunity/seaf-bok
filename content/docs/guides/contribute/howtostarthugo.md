---
title: "Как склонировать SEAF BOK и запустить локальный сервер HUGO"
weight: 12
# bookFlatSection: false
# bookToc: true
# bookHidden: false
bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
aliases:
  - Контрибьюторы SEAF BOK
---
# Установка PowerShell
TBD
# Клонирование локально репозитория SEAF BOK
TBD
# Запуск локального сервера HUGO
Для запуска локального сервера необходимо выполнить команду:
```
hugo server -D --renderToMemory
```

Если локальный веб-сервер не запускается, то можно выполнить обновление подмодулей (см. следующий раздел)

# Обновление подмодулей репозитория SEAF BOK

Если после клонирования локальный сервер Hugo не стартует, необходимо выполнить команду:
```
git submodule update --init --recursive
```

