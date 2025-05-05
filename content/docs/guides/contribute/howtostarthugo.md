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
# Установите PowerShell

# Cклонируйте локально репозиторий SEAF BOK

# Как запустить локальный сервер HUGO
Для запуска локального сервера необходимо выполнить команду:

```
hugo server -D --renderToMemory
```
Если локальный веб-сервер не запускается, то можно выполнить обновление подмодулей (см. следующий раздел)

# Как обновить подмодули репозитория Git SEAF BOK

Если после клонирования локальный сервер Hugo не стартует, необходимо выполнить команду:
```
git submodule update --init --recursive
```

