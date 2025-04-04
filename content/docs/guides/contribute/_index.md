---
title: How to Use & Contribute
weight: 8
bookCollapseSection: true
aliases:
  - Концепция SEAF.docs
tags:
  - docsascode
---
# Концепция управления документацией проекта SEAF.

Разработана концепция управления документацией SEAF с использованием двух методологических подходов:
- **"docs as code"** ("документация как код") и
- **Zettelkasten**, -
в совокупности обеспечивающих проект SEAF **возможностями интеллектуального управления идеями и документацией, создания контента для публикации на научных, технологических, развлекательных и любых других площадках.** 

С помощью выбранного подхода и современных поддерживающих его инструментов (Obsidian, плагины IDE, Hugo) реализуется "воронка"/"pipeline" для AI-native управления знаниями от идеи до реализации в инструменте.

## Правовые основы
1. Общие правовые основания появления, использование и развития SEAF Base Of Knowledge (SEAF BOK) физическими и юридическими лицами изложены в [SEAF On A Page](/docs/seafonapage).
2. Требования к разметке кода и контента для целей соблюдения требований авторского и исключительного права изложены в [**Как разметить статью или исходный код**](howtomarkdata)
3. Список [контрибьюторов](contributors)  SEAF BOK постоянно пополняется новыми участниками.

## Подход Docs as Code: сущность и преимущества

Подход Docs as Code представляет собой методологию разработки программной документации с использованием тех же инструментов и процессов, что применяются для написания кода. 
  
Ключевые компоненты подхода Docs as Code:  
- Использование упрощенных языков разметки (Markdown, reStructuredText, Asciidoc)
- Хранение документации в репозиториях Git
- Сборка публикуемой документации с помощью генераторов статических сайтов
- Применение CI/CD для автоматизации публикации

Основные преимущества данного подхода для проекта SEAF:
- **Вовлеченность разработчиков**: использование знакомых инструментов повышает желание участвовать в создании документации
- **Версионность**: контроль изменений документации аналогично контролю кода
- **Автоматизация**: непрерывная интеграция обеспечивает актуальность документации
- **Простота публикации**: автоматическое обновление веб-сайта при обновлении репозитория GIT
- **Экономичность**: использование общедоступных инструментов снижает стоимость[^1]

## Подход Zettelkasten для управления знаниями: сущность и преимущества

  ### Ключевые принципы Zettelkasten для SEAF:
- **Атомарность**: каждая заметка содержит только одну архитектурную концепцию или паттерн
- **Автономность**: заметки самодостаточны и понятны без контекста
- **Связанность**: создание явных связей между архитектурными концепциями
- **Уникальная идентификация**: каждый элемент фреймворка имеет свой ID
- **Пояснение связей**: объяснение логического обоснования связей между концепциями[^13]
  
  ### Практическая реализация в контексте SEAF

Для SEAF рекомендуется создание двух основных информационных графов:
 
1. **SEAF Fundamentals**: базовые концепции, принципы и модели архитектуры
2. **SEAF Guides**: практические руководства, примеры применения, шаблоны
 
Структура заметки должна включать:

- Уникальный идентификатор
- Название концепции/принципа
- Краткое описание (2-3 предложения)
- Подробное объяснение
- Ссылки на связанные концепции
- Метаданные (дата создания, автор, теги)[^2]

  
## Архитектура репозитория SEAF-BOK

  Для оптимальной организации документации SEAF предлагается федеративная модель с использованием Git submodules.
  
### Федеративная модель документации

Структура документации SEAF, включая SEAF Fundamentals и SEAF Guides, изложенная в составе SEAF On A Page: [**Структура документации SEAF**](../seafonapage/#seafdocstructure)

Федеративная модель предполагает распределение документации по нескольким репозиториям с централизованной точкой доступа. Этот подход особенно эффективен для автономных проектов под единым брендом, как в случае с SEAF[^8].
  
```

seaf-bok (основной репозиторий)
├── fundamentals (подмодуль -> seaf-fundamentals)
├── guides (подмодуль -> seaf-guides)
├── scripts (скрипты сборки и публикации)
├── themes (темы для статического сайта)
└── docs (сгенерированная документация для GitHub Pages)

```

  
### Использование Git Submodules

  Git submodules позволяют включать один репозиторий внутрь другого, сохраняя независимость истории изменений. Для SEAF-BOK этот подход обеспечивает:

  
1. Модульность: независимое развитие компонентов SEAF

2. Контроль версий: фиксация определенных версий документации

3. Управляемость: централизованный доступ через основной репозиторий[^10]

  
Пример команд для настройки:
  
```bash

# Создание основного репозитория
mkdir seaf-bok
cd seaf-bok
git init
git remote add origin https://github.com/организация/seaf-bok.git

# Добавление подмодулей
git submodule add https://github.com/организация/seaf-fundamentals.git fundamentals
git submodule add https://github.com/организация/seaf-guides.git guides
```


### Технические основания разработки SEAF BOK:
1. Процесс распределенной разработки SEAF с помощью публичного сервиса GitHub. GitHub Pages для документации SEAF. Короткие доменные имена.
2. Целевой репозиторий SEAF BOK и процесс распределенной разработки через форки
3. Что такое и зачем нужен Hugo
4. Процесс публикации документации SEAF Base Of Knowledge
5. Статусы заметок/документов: черновики и готовые к релизу. Где документы хранятся и как публикуются. Управление статусами любого артефакта в составе документации: страницы, изображения, любого другого ресурса страницы и т.д.
6. Теги заметок/документов. Принципы их ведения и набор 

 
### Инструмент для генерации сайта

  Для создания сайта SEAF (https://seaf.sci.community) используется **Hugo** по следующим причинам:
- **Высокая скорость**: генерация сайта из 2700 страниц за 500 мс (в сравнении с 90 секундами у Jekyll)
- **Гибкость шаблонов**: использование мощного языка Go для создания динамических шаблонов
- **Поддержка от Google**: активное развитие и поддержка сообщества
- **Наличие тем для документации**: специализированные темы Docsy, Learn и др.[^12] Для создания прототипа выбрана тема Book.

GitHub поддерживает HUGO через стандартные actions и проводит мониторинг как они работают в связке: https://jmooring.github.io/hugo-sites/, что делает инструмент легкодоступным сейчас и в будущем.

В Hugo и GitHub используют такие компании и проекты, как:

1. https://docs.ozon.ru/main/ (описание подхода к формированию документации доступно https://habr.com/ru/companies/ozontech/articles/695868/)
2. https://kubernetes.io/ (репозиторий https://github.com/kubernetes/website)
3. https://www.freebsd.org/
4. https://docs.docker.com/get-started/docker-overview/
5. https://gohugo.io/documentation/

### Настройка публикации на GitHub Pages
  
Для настройки публикации на GitHub Pages настроен GitHub Actions** - рабочий процесс, который запускается при обновлении ветки master [репозитория](https://github.com/Scicommunity/seaf-bok.git)


### Хранение медиафайлов Drawio

В репозитории хранятся исходные файлы в формате drawio для статических изображений.
В репозитории содержится папка .obsidian, содержащая файлы установленного плагина и его настройки (их изменять не требуется).
Рекомендуется использовать [плагин Diagrams Сообщества Obsidian](obsidian://show-plugin?id=drawio-obsidian) .

## Хранение медиафайлов Excalidraw

В репозитории хранятся исходные файлы в формате excalidraw для статических изображений.
Методика работы excalidraw, плагином в Obsidian [подробно описана здесь](https://excalidraw-obsidian.online/wiki/showcase).
В репозитории содержится папка .obsidian, содержащая файлы установленного плагина и его настройки.
Рекомендуется использовать [плагин Excalidraw Сообщества Obsidian](obsidian://show-plugin?id=obsidian-excalidraw-plugin) .



## Сравнительный анализ инструментов для работы с документацией

  

### IDE и расширения для работы с Zettelkasten

  

#### IntelliJ IDEA

  

**Markdown Navigator** - наиболее функциональный плагин для IntelliJ IDEA:

- Поддержка markdown с предпросмотром

- Интеграция с GitHub Wiki

- Навигация по ссылкам между заметками

- Поддержка TODO в markdown-комментариях[^4][^14]

  Преимущества IntelliJ IDEA для SEAF:

- Мощная интеграция с системами контроля версий
- Высокая функциональность для автодополнения и рефакторинга
- Поддержка множества языков программирования[^7]

#### Visual Studio Code

Наиболее подходящие расширения для Zettelkasten в VSCode:

- **Foam**: лучше всего работает с связанными заголовками и инлайн-ссылками

- **Dendron**: мощная иерархическая система заметок, но требует отдельного рабочего пространства

- **Markdown Memo**: хорошо справляется с связанными секциями и двунаправленными ссылками[^5]
 

Преимущества VSCode для SEAF:

- Легковесность и быстрота работы
- Большое количество расширений
- Простота настройки предпросмотра Markdown с разными темами[^7][^17]

#### Zed

  

Встроенные возможности Zed для работы с Markdown:

  

- Подсветка синтаксиса с использованием tree-sitter

- Языково-специфическая подсветка кода в блоках

- Интеграция с Prettier для форматирования

- Настраиваемые параметры обработки пробелов[^6]

  

Преимущества Zed:

  

- Высокая производительность при работе с большими документами

- Интеграция с AI для генерации и анализа документации

- Встроенные функции коллаборации для команды SEAF

  
  

### Рекомендуемый набор инструментов для команды SEAF

  

На основе анализа рекомендуется использовать:

  

1. **VSCode с расширением Foam** как основной редактор для большинства участников:

    - Наилучший баланс между функциональностью и простотой

    - Хорошая поддержка методологии Zettelkasten

    - Легковесность и быстрота работы

2. **IntelliJ IDEA с Markdown Navigator** для технических писателей и руководителей проекта:

    - Мощные возможности рефакторинга

    - Глубокая интеграция с Git

    - Управление проектами в одном интерфейсе

  



## Процесс квартальных релизов документации

  

Для обеспечения регулярных квартальных релизов документации SEAF рекомендуется следующий процесс:

  
### Планирование и подготовка релиза

  1. **Установка четкого графика релизов**:

    - Фиксированные даты релизов (например, первый день каждого квартала)

    - Разделение процесса на фазы (планирование, разработка, тестирование, публикация)

    - Выделение буферного времени для непредвиденных задержек[^11]

2. **Процесс обновления документации**:

    - Создание веток для новых версий документации

    - Разработка новых материалов в ветках feature/

    - Code review изменений в документации

    - Слияние изменений в основную ветку перед релизом

  
### Автоматизация релизов
 

1. **Использование тегов Git для версионирования**:

    - Создание тегов для каждого квартального релиза (например, `v2025-Q1`)

    - Обновление подмодулей до соответствующих тегов

2. **CI/CD для автоматизации публикации**:

    - Настройка GitHub Actions для автоматической сборки и публикации

    - Генерация примечаний к релизу (release notes)

    - Автоматическое обновление версии на сайте[^11]

  
### Документирование процесса релиза

  Для каждого релиза необходимо:
  
- Вести журнал изменений (CHANGELOG.md)

- Создавать документацию по миграции между версиями

- Сохранять историю предыдущих версий документации

  
  
## Примеры успешных проектов с подходом docs as code

  

### Архитектурная документация с arc42 и C4 Model

  

Проект milanm/architecture-docs демонстрирует генерацию архитектурной документации с использованием шаблона arc42, модели C4, Structurizr CLI и Asciidoctor. Данный подход может быть адаптирован для визуализации архитектурных концепций SEAF[^3].

  

### OpenTelemetry

  

OpenTelemetry использует федеративную модель документации, где центральный репозиторий документации импортирует контент из репозиториев кода с использованием git submodules. Этот подход особенно ценен для проектов с автономными компонентами, как в случае с SEAF[^8].

  

### Документация как сервис

  

Пример рабочего процесса, где CI/CD конвейеры генерируют исходники документации и публикуют их, используя отдельный репозиторий-сателлит. Это позволяет разделить контент и представление документации, что ценно для SEAF с его разделением на Fundamentals и Guides[^15].

  

## Заключение и рекомендации

  

На основе проведенного исследования для управления документацией проекта SEAF рекомендуется:

  

1. **Архитектура документации**:

    - Федеративная модель с использованием Git submodules

    - Разделение на репозитории SEAF Fundamentals и SEAF Guides

    - Контроль доступа на уровне организации GitHub

2. **Методология и инструменты**:

    - Zettelkasten для организации связанных архитектурных знаний

    - VSCode с Foam для большинства участников команды

    - IntelliJ IDEA с Markdown Navigator для продвинутых пользователей

3. **Публикация и релизы**:

    - Hugo для генерации статического сайта

    - GitHub Actions для автоматизации процесса публикации

    - Квартальные релизы с использованием тегов Git и автоматизации

  

Такой подход обеспечит эффективное управление документацией SEAF, сочетая преимущества docs as code с методологией Zettelkasten для создания взаимосвязанной базы знаний архитектурного фреймворка.

  

<div style="text-align: center">⁂</div>

  

[^1]: https://progdoc.ru/news/dokumentatsiya-kak-kod-docs-as-code/

  

[^2]: https://www.youtube.com/watch?v=jbvEJvTwllk

  

[^3]: https://github.com/milanm/architecture-docs

  

[^4]: https://gist.github.com/maenujem/f9dce9d1eec42696643658bc7d93dd93

  

[^5]: https://www.reddit.com/r/Zettelkasten/comments/1044bb1/best_obsidianlike_extensions_for_vscode/

  

[^6]: https://zed.dev/docs/languages/markdown

  

[^7]: https://sky.pro/wiki/javascript/luchshie-ide-dlya-razrabotki-sravnenie-i-vybor/

  

[^8]: https://passo.uno/docs-as-code-topologies/

  

[^9]: https://www.jot.fm/issues/issue_2003_05/article4.pdf

  

[^10]: https://thebottleneckdev.com/blog/monorepo-git-submodules

  

[^11]: https://zeet.co/blog/software-release-management-best-practices

  

[^12]: https://idratherbewriting.com/learnapidoc/pubapis_static_site_generators.html

  

[^13]: https://dzen.ru/a/YCJHa9HQGgz4yin8

  

[^14]: https://github.com/vsch/idea-multimarkdown/wiki/Adding-GitHub-Wiki-to-IntelliJ-Project

  

[^15]: https://habr.com/ru/companies/yadro/articles/785766/

  

[^16]: https://docs.github.com/ru/enterprise-server@3.12/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

  

[^17]: https://stackoverflow.com/questions/55180020/set-background-color-on-visual-studio-code-markdown-preview

  

[^18]: https://na-journal.ru/5-2023-informacionnye-tekhnologii/5036-avtomatizaciya-processa-sozdaniya-tekhnicheskoi-dokumentacii-na-osnove-podhoda-docs-as-code

  

[^19]: https://ru.hexlet.io/blog/posts/chto-takoe-framework

  

[^20]: https://sky.pro/wiki/profession/dokumentaciya-kak-kod-v-devops/

  

[^21]: https://www.codecentric.de/knowledge-hub/blog/architecture-documentation-as-code-with-structurizr-and-asciidoctor-part-2-asciidoctor

  

[^22]: https://tproger.ru/articles/documentation-as-code-praktiki-i-instrumenty-dokumentirovaniya-v-sfere-finansovyh-tehnologij

  

[^23]: https://techwrconsult.com/dokumentaciya-kak-kod

  

[^24]: https://community.exolve.ru/blog/swagger-chto-eto-kak-rabotat-s-dokumentatsiey/

  

[^25]: https://habr.com/ru/companies/basis/articles/875942/

  

[^26]: https://habr.com/ru/articles/726428/

  

[^27]: https://tproger.ru/articles/pochemu-as-code---eto-ne-prosto-trend--a-novaya-realnost-razrabotki

  

[^28]: https://platformv.sbertech.ru/blog/kak-perejti-na-docs-as-a-code-i-kakie-instrumenty-dlya-etogo-ispolzovat

  

[^29]: https://learn.microsoft.com/ru-ru/dotnet/visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods

  

[^30]: https://carbonfay.ru/directions/razrabotka-dokumentacii-docs-as-a-code/

  

[^31]: https://github.com/SEAFTeam/seaf-core

  

[^32]: https://habr.com/ru/companies/zyfra/articles/578486/

  

[^33]: https://habr.com/ru/companies/moysklad/articles/854708/

  

[^34]: https://developers.webasyst.ru/docs/cookbook/basics/

  

[^35]: https://longcatdev.com/blog/dokumentaciya_koda

  

[^36]: https://www.youtube.com/watch?v=MWxqtzhlPYc

  

[^37]: https://habr.com/ru/articles/508672/

  

[^38]: https://habr.com/ru/articles/834514/

  

[^39]: https://vc.ru/u/1778608-evgeny-popov/782109-zettelkasten-ispolzuite-etot-podhod-dlya-effektivnogo-nakopleniya-znanii

  

[^40]: https://ast-academy.ru/blog/vtoroj-mozg-i-zettelkasten-kak-organizovat-svoi-znania-i-stat-produktivnee/

  

[^41]: https://ru.wikipedia.org/wiki/Цеттелькастен

  

[^42]: https://forum.obsidian.md/t/developers-how-are-you-storing-technical-information/34505

  

[^43]: https://cyberleninka.ru/article/n/personalnye-bazy-znaniy-i-metod-zettelkasten-kak-sposob-organizatsii-znaniy

  

[^44]: https://yourchoice.ru/obraz-zhizni/zametki-o-tom-kak-delat-zametki-chto-takoe-zettelkasten-i-kak-luchshe-vsego-delat-zapisi.htm

  

[^45]: https://tenchat.ru/media/1880299-metodologiya-zettelkasten

  

[^46]: https://vas3k.club/post/3040/

  

[^47]: https://www.zoho.com/workplace/articles/zettelkasten-method.html

  

[^48]: https://hermongroup.ru/blog/tpost/h3g8sboyr1-metod-zettelkasten-umnoe-vedenie-zametok

  

[^49]: https://habr.com/ru/companies/yadro/articles/835664/

  

[^50]: https://научныепереводы.рф/metod-zettelkasten/

  

[^51]: https://knowledgeconf.ru/2022/abstracts/8414

  

[^52]: https://zenkit.com/en/blog/a-beginners-guide-to-the-zettelkasten-method/

  

[^53]: https://productuniversity.ru/zettelkasten

  

[^54]: https://fedorovpishet.ru/pyat-nedostatkov-zettelkasten/

  

[^55]: https://starkovden.github.io/Switching-tools.html

  

[^56]: https://habr.com/ru/articles/854230/

  

[^57]: https://www.codecentric.de/wissens-hub/blog/architecture-documentation-docs-as-code-structurizr-asciidoctor

  

[^58]: https://docs.github.com/ru/contributing/writing-for-github-docs/using-markdown-and-liquid-in-github-docs

  

[^59]: https://github.com/bflorat/architecture-document-template

  

[^60]: https://www.writethedocs.org/guide/docs-as-code.html

  

[^61]: https://github.com/devopshq/ExampleProject/blob/master/README.md

  

[^62]: https://github.com/garywhiteford/whatIknow/blob/main/docs/Notes-Enterprise_Architecture_Foundations.md

  

[^63]: https://www.qt.io/quality-assurance/blog/critical-role-of-software-architecture

  

[^64]: https://habr.com/ru/companies/ozontech/articles/695868/

  

[^65]: https://habr.com/ru/companies/plesk/articles/555110/

  

[^66]: https://capgemini.github.io/architecture/enterprise-architecture-docops/

  

[^67]: https://www.reddit.com/r/devops/comments/mmuk4j/documentation_as_code/

  

[^68]: https://github.com/doka-guide/content/blob/main/tools/markdown/index.md

  

[^69]: https://javarush.com/groups/posts/3146-10-poleznihkh-plaginov-dlja-intellij-idea-dlja-novichkov-i-opihtnihkh-razrabotchikov

  

[^70]: https://habr.com/ru/companies/spring_aio/articles/826930/

  

[^71]: https://github.com/cronn/validation-files-comparison-intellij-plugin

  

[^72]: https://amplicode.ru/blog/giga-ide-overview/

  

[^73]: https://blog.jetbrains.com/ru/idea/2021/06/top-10-plugins-for-intellij-idea/

  

[^74]: https://www.jetbrains.com/help/idea/markdown.html

  

[^75]: https://apidog.com/blog/api-debugging-tools-in-intellij-idea/

  

[^76]: https://plugins.jetbrains.com/plugin-ideas/search?sorting=Votes

  

[^77]: https://tproger.ru/experts/plugins-for-ide

  

[^78]: https://habr.com/ru/articles/768238/comments/

  

[^79]: https://habr.com/ru/articles/873132/

  

[^80]: https://blog.jetbrains.com/platform/2023/02/top-10-plugins-for-intellij-based-ides/

  

[^81]: https://freedocs.mi.hdm-stuttgart.de/sdi_sect_ideaBaseUsage.html

  

[^82]: https://garden.struchkov.dev/ru/dev/java/Лучшие-и-полезные-плагины-для-IntelliJ-IDEA-2024

  

[^83]: https://fedorovpishet.ru/pimp-my-obsidian/

  

[^84]: https://github.com/vsch/idea-multimarkdown

  

[^85]: https://digma.ai/25-best-intellij-idea-plugins-for-developers-in-2023/

  

[^86]: https://stackoverflow.com/questions/75446960/azure-devops-wiki-how-to-link-inside-a-page

  

[^87]: https://018.kz/ru/4638-desjat-neobhodimyh-plaginov-dlja-povyshenija-produktivnosti-v-intellij-idea-v-2024.html

  

[^88]: https://www.reddit.com/r/Zettelkasten/comments/hmlxvh/vscode_memo_markdown_knowledge_base_with/

  

[^89]: https://packmind.com/vscode-extensions-technical-team-knowledge-sharing/

  

[^90]: https://proglib.io/p/10-nezamenimyh-plaginov-dlya-vs-code-2024-06-24

  

[^91]: https://wiki.dendron.so/notes/9Id5LUZFfM1m9djl6KgpP/

  

[^92]: https://habr.com/ru/articles/698702/

  

[^93]: https://code.visualstudio.com/docs/languages/markdown

  

[^94]: https://razorpay.com/learn/vs-code-as-a-documentation-tool/

  

[^95]: https://dzen.ru/a/Znkp0uFfEimNKwOe

  

[^96]: https://news.ycombinator.com/item?id=30153067

  

[^97]: https://github.com/nergal-perm/zettelkasten-vscode

  

[^98]: https://marketplace.visualstudio.com/items?itemName=Successible.markdown-wiki

  

[^99]: https://www.syncfusion.com/blogs/post/top-vs-code-extensions

  

[^100]: https://tenchat.ru/media/1953585-rasshireniya-visual-studio-code-dlya-povysheniya-vashu-proizvoditelnosti-v-2024-godu

  

[^101]: https://news.ycombinator.com/item?id=31304441

  

[^102]: https://genius.courses/топ-50-расширении-для-vs-code/

  

[^103]: https://marketplace.visualstudio.com/items?itemName=thomaskoppelaar.markdown-wiki-links-preview

  

[^104]: https://code.visualstudio.com/docs

  

[^105]: https://habr.com/ru/companies/ru_mts/articles/825234/

  

[^106]: https://notes.dt.in.th/20201108T202126Z2125

  

[^107]: https://opennet.ru/60495-zed

  

[^108]: https://www.youtube.com/watch?v=SB95PCjaiNs

  

[^109]: https://zed.dev/ai

  

[^110]: https://blog.kodezi.com/zed-vs-vs-code-a-comprehensive-comparison-of-features-and-usability/

  

[^111]: https://opennet.ru/61524-zed

  

[^112]: https://htmlacademy.ru/blog/soft/editors-for-the-coders-in-2025

  

[^113]: https://github.com/zed-industries/zed/discussions/8257

  

[^114]: https://zed.dev/blog/zed-ai

  

[^115]: https://www.reddit.com/r/ZedEditor/comments/1g7b6vm/zed_vs_vscode_looking_for_insights/

  

[^116]: https://apptractor.ru/info/news/zed.html

  

[^117]: https://www.linux.org.ru/news/opensource/17672817/page3

  

[^118]: https://dev.to/gimalay/markdown-notes-assistant-with-extractinline-refactoring-1947

  

[^119]: https://codeparrot.ai/blogs/ai-ready-code-editor-this-is-zed-editor-for-beginners

  

[^120]: https://github.com/zed-industries/zed/discussions/6575

  

[^121]: https://pingvinus.ru/news/5189

  

[^122]: https://zed.dev/extensions

  

[^123]: https://www.grailbox.com/2024/09/editing-markdown-in-zed/

  

[^124]: https://zed.dev/blog/building-a-text-editor-in-times-of-ai

  

[^125]: https://news.ycombinator.com/item?id=31669785

  

[^126]: https://followmentalgarden.substack.com/p/6-best-notes-apps-for-zettelkasten

  

[^127]: https://pdf.wondershare.com.ru/create-pdf/online-markdown-editor.html

  

[^128]: https://niftypm.com/blog/best-document-comparison-tools/

  

[^129]: https://sky.pro/wiki/javascript/sravnenie-ide-i-redaktorov-koda-po-stoimosti/

  

[^130]: https://www.youtube.com/watch?v=g9AGVLLhHyc

  

[^131]: https://zk.zettel.page/software-list

  

[^132]: https://www.ixbt.com/soft/markdown-online-1.shtml

  

[^133]: https://daily.dev/blog/10-best-api-documentation-tools-2024

  

[^134]: https://www.reddit.com/r/rusAskReddit/comments/1j6ji0f/лучший_редактор_кодаide_по_вашему_мнению/

  

[^135]: https://forum.zettelkasten.de/discussion/1108/help-me-pick-an-editor

  

[^136]: https://www.markdowntoolbox.com/ru/блог/редактор-markdown-с-просмотром-основными-функциями/

  

[^137]: https://canadian.agency/best-software-documentation-tools/

  

[^138]: https://www.youtube.com/watch?v=h7y3nB7gWsE

  

[^139]: https://pdf.wondershare.com.ru/create-pdf/best-markdown-editor.html

  

[^140]: https://spider-themes.net/eazydocs/eazydocs-vs-wedocs/

  

[^141]: http://techwriters.ru/ru/tools_and_technologies/docs_as_code.html

  

[^142]: https://docs.github.com/ru/get-started/learning-about-github/access-permissions-on-github

  

[^143]: https://docsvision.com/info-centr/articles/elektronnyy-arhiv-tehnicheskih-dokumentov-vozmozhnosti-preimuschestva-etapy-sozdaniya.html

  

[^144]: https://resources.github.com/learn/pathways/administration-governance/essentials/structural-components-of-github-enterprise-cloud/

  

[^145]: https://habr.com/ru/companies/alfa/articles/757872/

  

[^146]: https://ru.stackoverflow.com/questions/961723/Доступ-к-приватному-репозиторию-на-github-для-других-участников

  

[^147]: https://digdes.ru/blog/elektronnyj-arhiv-tehnicheskih-dokumentov

  

[^148]: https://idratherbewriting.com/2017/08/23/content-architecture-and-repo-sizes/

  

[^149]: https://resources.github.com/learn/pathways/administration-governance/essentials/strategies-for-using-organizations-github-enterprise-cloud/

  

[^150]: https://docs.github.com/ru/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository

  

[^151]: https://www.astera.com/ru/type/blog/data-repository/

  

[^152]: https://github.com/beyondcode/docs-example

  

[^153]: https://github.blog/enterprise-software/devops/best-practices-for-organizations-and-teams-using-github-enterprise-cloud/

  

[^154]: https://docs.github.com/ru/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories

  

[^155]: https://habr.com/ru/companies/arenadata/articles/813487/

  

[^156]: https://my.e.donstu.ru/g/help/development/documentation/site_architecture/folder_structure.md

  

[^157]: https://docs.github.com/organizations

  

[^158]: https://pionerov.ru/assets/downloads/mc/recommendations/doop-shablon.pdf

  

[^159]: https://habr.com/ru/companies/swordfish_security/articles/754780/

  

[^160]: https://www.reddit.com/r/git/comments/snz2p8/best_practices_for_a_single_repositorie_with/

  

[^161]: https://markirovka.ru/knowledge/tovarnye-gruppy/obschie-voprosy-gis/formaty-razreshitelnykh-dokumentov

  

[^162]: https://en.wikipedia.org/wiki/Federated_architecture

  

[^163]: https://www.concord.app/blog/document-repository-best-practices/

  

[^164]: https://blog.cloudflare.com/our-docs-as-code-approach/

  

[^165]: https://synergy.ru/akademiya/programming/chto_takoe_patternyi_proektirovaniya_v_programmirovanii

  

[^166]: https://atlan.com/federated-architecture/

  

[^167]: https://selectel.ru/blog/tutorials/git-setup-and-common-commands/

  

[^168]: https://start.docuware.com/blog/document-management/what-is-a-document-repository-benefits-set-up-tips-and-best-practices

  

[^169]: https://about.gitlab.com/blog/2022/10/12/five-fast-facts-about-docs-as-code-at-gitlab/

  

[^170]: https://www.consultant.ru/document/cons_doc_LAW_112673/6e1337c3c4411ad5d4e6f0d29efcc70003edef25/

  

[^171]: https://federatedplatforms.eu/images/Library/Activity2/FEDeRATED_Reference_Architecture.pdf

  

[^172]: https://timeweb.cloud/tutorials/microservices/otdelnye-repozitorii-ili-monorepozitorii

  

[^173]: https://stackoverflow.com/questions/30188252/where-to-put-documentation-relating-to-multiple-git-repos

  

[^174]: https://jfrog.com/help/r/jfrog-artifactory-documentation/federated-repositories

  

[^175]: https://git-scm.com/book/ru/v2/Инструменты-Git-Подмодули

  

[^176]: https://gitverse.ru/docs/repositories/repository-submodules-uc/

  

[^177]: https://javanexus.com/blog/managing-complex-git-submodules-best-practices

  

[^178]: https://stackoverflow.com/questions/75588751/implementing-semantic-versioning-with-git-submodules

  

[^179]: https://www.atlassian.com/ru/git/tutorials/git-submodule

  

[^180]: https://habr.com/ru/articles/488956/

  

[^181]: https://blog.pixelfreestudio.com/best-practices-for-using-git-submodules/

  

[^182]: https://stackoverflow.com/questions/46462610/monorepo-vs-git-submodules

  

[^183]: https://www.diversion.dev/blog/git-unreal-engine-semantic-versioning-plugins-and-git-submodules

  

[^184]: https://habr.com/ru/companies/relex/articles/258505/

  

[^185]: https://algocademy.com/blog/using-git-submodules-for-large-scale-projects-a-comprehensive-guide/

  

[^186]: https://www.reddit.com/r/node/comments/n1mw61/monorepo_or_not/

  

[^187]: https://labex.io/tutorials/git-how-to-track-git-submodule-versions-418103

  

[^188]: https://codex.so/git-submodules

  

[^189]: https://www.aviator.co/blog/managing-repositories-with-git-submodules/

  

[^190]: https://dev.to/davidarmendariz/git-submodules-vs-monorepos-14h8

  

[^191]: https://git-scm.com/docs/git-submodule

  

[^192]: https://idratherbewriting.com/2017/06/02/when-docs-are-not-like-code/

  

[^193]: https://www.hatica.io/blog/automating-documentation-with-github-actions/

  

[^194]: https://infostart.ru/1c/articles/1294112/

  

[^195]: https://david.pilato.fr/posts/2023-01-12-automatically-update-documentation-with-github-actions/

  

[^196]: https://pronovix.com/blog/cicd-and-docs-code-workflow

  

[^197]: https://techcommunity.microsoft.com/blog/educatordeveloperblog/docaider-automated-documentation-maintenance-for-open-source-github-repositories/4245588

  

[^198]: https://www.atlassian.com/agile/product-management/product-release

  

[^199]: https://dev.to/nasrulhazim/automate-update-your-changelog-with-github-actions-5g10

  

[^200]: https://redocly.com/blog/git-branching-for-docs

  

[^201]: https://document360.com/blog/release-management-process/

  

[^202]: https://docs.github.com/en/issues/planning-and-tracking-with-projects/automating-your-project/using-the-built-in-automations

  

[^203]: https://arxiv.org/abs/2409.02366

  

[^204]: https://www.altexsoft.com/blog/technical-documentation-in-software-development-types-best-practices-and-tools/

  

[^205]: https://documenterra.ru/release-notes-poshagovoe-rukovodstvo/

  

[^206]: https://www.smashingmagazine.com/2021/08/automate-documentation-workflow-for-developers/

  

[^207]: https://notissimus.com/top-6-generatorov-staticheskih-sajtov-react-kotorye-stoit-rassmotret-v-2023-godu/

  

[^208]: https://docsy-site.netlify.app/docs/static-site-generators/docs-as-code/

  

[^209]: https://habr.com/ru/articles/532738/

  

[^210]: https://overcast.blog/11-documentation-website-generators-you-should-know-37eb7da6f36b

  

[^211]: https://www.reddit.com/r/technicalwriting/comments/14rksvi/which_ssg_would_you_recommend_for_a_knowledge_base/

  

[^212]: https://web-f.ru/vybor-mezhdu-gatsby-i-next-js-v-2022-godu/

  

[^213]: https://www.lambdatest.com/blog/top-static-site-generators/

  

[^214]: https://soft-app-news.ru/reviews/static-site-generator-hugo/

  

[^215]: https://github.com/myles/awesome-static-generators

  

[^216]: https://github.com/docops-hq/learnapidoc-ru/blob/master/Publishing-doc/Static-site-generators.md

  

[^217]: https://envybox.io/blog/top-30-konstruktorov-sajtov-2024-goda-kriterii-vybora-i-obzor-luchshih-platform/

  

[^218]: https://www.reddit.com/r/technicalwriting/comments/1bj3ied/whats_your_favorite_static_site_generator/

  

[^219]: https://aappss.ru/p/hugo/

  

[^220]: https://jochenschroeder.com/blog/articles/a-comparison-of-static-site-generators/

  

[^221]: https://habr.com/ru/companies/documentat/articles/862522/

  

[^222]: https://habr.com/ru/articles/779428/

  

[^223]: https://dev.to/themeselection/static-site-generator-1fp4

  

[^224]: https://habr.com/ru/articles/700640/

  

[^225]: https://github.com/collections/static-site-generators

  

[^226]: https://dzen.ru/a/Ywn4URqip16t7KF6

  

[^227]: https://shtab.app/blog/primiery-kanban-protsiessov-nie-v-it-ot-zdravookhranieniia-do-stroitielstva/

  

[^228]: https://habr.com/ru/articles/509756/

  

[^229]: https://habr.com/ru/articles/715542/

  

[^230]: https://engineer.yadro.com/note/zettelkasten-2/

  

[^231]: https://netpeak.net/ru/blog/vtoroy-mozg-gayd-po-sisteme-umnykh-zametok-zettelkasten-pervaya-chast/

  

[^232]: https://otus.ru/journal/proekt-plugin-for-obsidian-kursa-arhitektura-i-shablony-proektirovaniya/

  

[^233]: https://fedorovpishet.ru/real-zettelkasten/

  

[^234]: https://engineer.yadro.com/note/zettelkasten/

  

[^235]: https://habr.com/ru/articles/779804/

  

[^236]: https://companies.rbc.ru/news/PiP56d69na/metod-zettelkasten---kak-razobratsya-v-svoih-zametkah/

  

[^237]: https://productuniversity.ru/zettelkasten-method

  

[^238]: https://intellij-support.jetbrains.com/hc/en-us/community/posts/360010605419-Navigating-from-Markdown-reST-to-code

  

[^239]: https://www.dokuwiki.org/plugin:backlinks

  

[^240]: https://forum.obsidian.md/t/obsidian-plugin-for-building-a-digital-zettelkasten-or-personal-knowledge-management-pkm-system/85619

  

[^241]: https://blog.jetbrains.com/idea/2024/06/10-plugins-to-enhance-your-intellij-idea-experience-in-2024/

  

[^242]: https://marketplace.opentext.com/appdelivery/content/jetbrains-intellij-idea-plugin-for-valueedge

  

[^243]: https://www.xda-developers.com/best-personal-knowledge-management-tools-maximum-privacy/

  

[^244]: https://packmind.com/intellij-extensions-knowledge-sharing/

  

[^245]: https://habr.com/ru/articles/270309/

  

[^246]: https://www.jetbrains.com/help/idea/text-direction.html

  

[^247]: http://developerlife.com/2020/11/20/idea-plugin-example-intro/

  

[^248]: https://dev.to/auden/top-10-intellij-idea-plugins-to-boost-development-efficiency-in-2024-1o9o

  

[^249]: https://www.linkedin.com/posts/mischavandenburg_skool-community-update-june-2024-activity-7208085679522615298-TTym

  

[^250]: https://habr.com/ru/articles/486578/

  

[^251]: https://youtrack-support.jetbrains.com/hc/en-us/community/posts/360010246160-How-to-link-to-other-KnowledgeBase-articles

  

[^252]: https://www.reddit.com/r/IntelliJIDEA/comments/1baq0ju/something_like_obsidian_notetaking_app_but_with/

  

[^253]: https://sky.pro/wiki/html/generatory-sajtov-kak-oni-rabotayut-i-zachem-nuzhny/

  

[^254]: https://kinsta.com/blog/static-site-generator/

  

[^255]: https://docs.github.com/ru/enterprise-cloud@latest/actions/sharing-automations/creating-actions/publishing-actions-in-github-marketplace

  

[^256]: https://www.youtube.com/watch?v=GHOZTre6m3A

  

[^257]: https://sky.pro/wiki/html/instrumenty-dlya-sozdaniya-sajtov-tekstovye-redaktory/

  

[^258]: https://www.codica.com/blog/top-10-static-site-generators-to-build-websites/

  

[^259]: http://www.sasgis.org/mantis/print_all_bug_page.php

  

[^260]: https://habr.com/ru/articles/733868/

  

[^261]: https://about.gitlab.com/blog/2022/04/18/comparing-static-site-generators/

  

[^262]: https://starkovden.github.io/Doc-as-code-tools.html

  

[^263]: https://www.phys.msu.ru/rus/research/reports/PUBLICATIONS/sp_publ_2013.pdf

  

[^264]: https://www.lucidchart.com/pages/ru/examples/workflow-maker

  

[^265]: https://leftjoin.ru/blog/data-engineering/github-api/

  

[^266]: https://ssau.ru/docs/sveden/education/Metod_Disc_FUNMATIMEKH-FMIP-SPEC-O-PP_2019.pdf

  

[^267]: https://docs.simpleone.ru/ru/platform/1.23.3/developer-help/business-logic/workflows/workflow-activities

  

[^268]: https://docs.github.com/ru/actions/sharing-automations/sharing-actions-and-workflows-from-your-private-repository

  

[^269]: https://www.imemo.ru/files/File/magazines/puty_miru/2024/01/FullText-01-2024-Full1.pdf

  

[^270]: https://habr.com/ru/companies/slurm/articles/723608/

  

[^271]: https://learn.microsoft.com/ru-ru/azure/storage/blobs/storage-blobs-static-site-github-actions

  

[^272]: https://docs.github.com/ru/enterprise-cloud@latest/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

  

[^273]: https://dev.to/pratik_kale/github-pages-custom-domains-and-ssl-mc4

  

[^274]: https://synergy.ru/akademiya/programming/kak_razmestit_sajt_na_github_pages_za_prostyix_shagov

  

[^275]: https://timeweb.cloud/tutorials/ci-cd/pajplajn-ci-cd-chto-ehto-takoe

  

[^276]: https://docs.github.com/ru/enterprise-cloud@latest/actions/use-cases-and-examples/deploying/deploying-to-azure-static-web-app

  

[^277]: https://vite-docs-ru.vercel.app/guide/static-deploy.html

  

[^278]: https://zlonov.ru/howto-configure-custom-domain-for-GitHub-Pages/

  

[^279]: https://klimchuk.net/notes/static-blog-automation-hugo-circle-ci/

  

[^280]: https://habr.com/ru/articles/820451/

  

[^281]: https://www.youtube.com/watch?v=KQimnN1xMqY

  

[^282]: https://docs.github.com/articles/securing-your-github-pages-site-with-https

  

[^283]: https://varmara.github.io/ru/post/2019-01-15-deploying-a-hugo-based-website-on-github-user-pages/

  

[^284]: https://vladislaveremeev.gitbook.io/qa_bible/avtomatizaciya-beta/infrastruktura-i-paiplain-ci-cd

  

[^285]: https://docs.github.com/ru/actions/use-cases-and-examples/deploying/deploying-with-github-actions

  

[^286]: https://v1.docusaurus.io/docs/ru/1.14.4/publishing

  

[^287]: https://docs.github.com/ru/pages/configuring-a-custom-domain-for-your-github-pages-site

  

[^288]: https://habr.com/ru/articles/882388/

  

[^289]: https://www.lode.de/blog/optimizing-your-writing-desk-setup-ergonomics-essentials

  

[^290]: https://gb.ru/blog/redaktory-koda/

  

[^291]: https://www.youtube.com/watch?v=YG4dVK6GOUk

  

[^292]: https://pydata-sphinx-theme.readthedocs.io/en/stable/user_guide/light-dark.html

  

[^293]: https://www.youtube.com/watch?v=ze9u29hTF70

  

[^294]: https://htmlacademy.ru/blog/soft/vs-code-themes

  

[^295]: https://zed.dev/docs/configuring-zed

  

[^296]: https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/

  

[^297]: https://www.descript.com/blog/article/ergonomics-principles-for-video-editors-from-an-instagram-pt

  

[^298]: https://it-incubator.io/lt/blog/best-code-editors

  

[^299]: https://github.com/kpitt/zed-theme-intellij-newui/blob/main/README.md

  

[^300]: https://www.stefanjudis.com/notes/how-to-define-dark-light-mode-images-in-github-markdown/

  

[^301]: https://www.worksafenb.ca/media/61622/computer_workstation_ergonomics.pdf





7. Как документация создавалась
Что такое и зачем нужен Obsidian
Что такое и зачем нужен Zettelcasten

Другие расширения в IDE для создания документации в obsidian style.То есть Obsidian не является чем-то обязательным. Просто удобным, как опция для работы
Поклонники Zettelcasten среди нас



Релевантные статьи:
1. [Как начать пользоваться SEAF BOK](howtostart)
2. [Как оформить статью SEAF BOK](howtoformat)
3. [Как добавить статью SEAF BOK](howtoadd)
4. [Актуальные задачи](todolist)
5. [Система тегов](tags)

Включить контент:

![Как начать пользоваться SEAF BOK](howtostart.md)

![todolist](todolist.md)

![Концепция DocsAsCode](content/docs/contribute/_index.md)

![todolist](todolist.md)



