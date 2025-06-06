---
title: "CodeSmell"
weight: 002
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Феномен низкокачественного программирования и его влияние на разработку

---

"Говнокодеры" представляют собой специфическую категорию разработчиков, чья деятельность характеризуется систематическим созданием кода низкого качества, игнорированием лучших практик и сопротивлением улучшениям. Их работа часто приводит к накоплению технического долга, снижению скорости разработки и увеличению операционных рисков. Несмотря на это, такие специалисты умеют позиционировать свои решения как «быстрые победы», маскируя долгосрочные проблемы под сиюминутные выгоды. В данном исследовании анализируются принципы их работы, механизмы влияния на команды и стратегии противодействия, включая международные аналоги явления.

---

## Определение и идентификация говнокодеров

### Ключевые характеристики говнокодера

Говнокодер — это программист, чей код более чем на 50% состоит из элементов, нарушающих базовые принципы проектирования, читаемости и поддерживаемости[^1]. Его отличительными чертами являются:

- **Нежелание рефакторить код**: сопротивление любым попыткам улучшения существующей кодовой базы, даже при явных признаках её неэффективности.
- **Игнорирование стандартов**: пренебрежение PEP 8, SOLID-принципами и другими общепринятыми руководствами, что приводит к фрагментарности и противоречивости стиля[^6].
- **Агрессивная реакция на критику**: вместо конструктивного диалога говнокодеры склонны защищать свои решения, часто апеллируя к «оперативности» выполнения задач[^2].

Пример из практики: в статье на Habr описывается случай, когда код Серёжи, типичного говнокодера, вызывал шок у коллег своей запутанностью, но при этом неожиданно работал, создавая иллюзию функциональности[^3].

### Психологический портрет

Говнокодеры часто страдают от **когнитивных искажений**, таких как:

- **Эффект Даннинга-Крюгера**: переоценка собственных компетенций при отсутствии навыков рефлексии.
- **Синдром самозванца**: парадоксальное сочетание агрессивной защиты своего кода с внутренними сомнениями, компенсируемыми гипертрофированной самоуверенностью.
- **Страх замены**: убеждённость, что только они способны поддерживать созданный ими же хаос[^2].

---

## Принципы написания кода

### Тактика «быстро и грязно»

Говнокодеры сознательно выбирают подходы, минимизирующие время на проектирование, но максимизирующие немедленный результат:

1. **Жёсткая связность (high coupling)**: компоненты системы тесно переплетены, что делает невозможным изолированное тестирование или модификацию.
2. **Дублирование кода**: повторяющиеся фрагменты вместо создания универсальных функций или классов.
3. **Магические числа и строки**: использование «захардкоженных» значений без пояснений, усложняющих понимание логики[^6].

Пример из источника[^3]: алгоритм, занимавший 10 000 строк кода и покрывавший лишь 0.002% возможных сценариев, был переписан в 100 строк после вмешательства квалифицированного разработчика.

### Отказ от документирования

В отличие от учеников, которые признают свои ошибки и стремятся к улучшениям[^1], говнокодеры избегают:

- Комментариев, объясняющих неочевидные решения.
- Технических спецификаций, фиксирующих требования.
- Чистых интерфейсов с чёткими контрактами.

Это создаёт **информационный вакуум**, где только автор кода понимает его работу, искусственно повышая свою незаменимость.

---

## Обоснование пользы и манипуляции восприятием

### Аргументация для руководства

Говнокодеры эксплуатируют **краткосрочные метрики**, чтобы доказать свою ценность:

- **Скорость доставки**: акцент на количестве закрытых задач в ущерб их качеству.
- **Минимизация затрат**: отказ от тестирования, рефакторинга и автоматизации ради «экономии» ресурсов.
- **Подмена понятий**: представление технического долга как «гибкости» или «адаптивности» системы[^5].

Кейс из статьи на Infostart: клиенты Серёжи, говнокодера, в итоге разрешили другим разработчикам работать над их задачами, осознав, что первоначальная «оперативность» обернулась ростом долгосрочных расходов[^2].

### Создаваемые иллюзии

Руководство, не обладающее технической экспертизой, часто становится жертвой:

- **Иллюзии контроля**: вера в то, что кодовая база остаётся управляемой, несмотря на растущую энтропию.
- **Заблуждение о масштабируемости**: уверенность, что система выдержит рост нагрузки без архитектурных изменений.
- **Миф о «быстрой победе»**: восприятие говнокода как временного решения, хотя на практике он становится постоянным[^4].

---

## Влияние на команду и архитектуру

### Деморализация квалифицированных разработчиков

- **Увеличение нагрузки**: исправление ошибок и декодирование непонятной логики отнимает до 40% времени[^5].
- **Эрозия стандартов**: новые члены команды перенимают плохие практики, считая их нормой.
- **Конфликты**: попытки внедрить лучшие практики сталкиваются с сопротивлением говнокодеров, что приводит к токсичной атмосфере[^3].


### Риски для архитектуры

- **Невозможность рефакторинга**: сильная связность компонентов делает изменения рискованными и дорогостоящими.
- **Технический долг**: по оценкам из Hacker News, компании тратят 18+ месяцев на постепенную переработку говнокода, что замедляет выход новых функций[^5].
- **Потеря гибкости**: система становится «монолитом», неспособным адаптироваться к меняющимся требованиям.

---

## Аналоги в англоязычной практике

### «Shitty code» и «Cowboy coding»

В западных источниках явление описывается терминами:

- **Shitty code**: код с низкой читаемостью, непредсказуемым поведением и высоким риском ошибок[^5].
- **Cowboy coding**: стиль разработки без плана, тестирования или согласования с командой, аналогичный «ковбойской» методологии[^7].

Пример из Hacker News: стартап, столкнувшийся с необходимостью 18-месячного рефакторинга из-за накопленного технического долга, потерял возможность быстро реагировать на запросы рынка[^5].

### Культурные различия

- **Акцент на метриках**: в англоязычных источниках чаще предлагают量化评估 качества кода (например, через цикломатическую сложность) для объективной аргументации[^3].
- **Роль процессов**: внедрение code review и CI/CD рассматривается как обязательное условие борьбы с низкокачественным кодом[^6].

---

## Рекомендации по противодействию

### Тактики для команд

1. **Внедрение код-ревью**: обязательная проверка всеми членами команды, исключающая слияние непроверенного кода.
2. **Метрики качества**: использование инструментов вроде SonarQube для отслеживания технического долга, покрытия тестами и сложности функций.
3. **Парное программирование**: вовлечение говнокодеров в работу с опытными коллегами для передачи знаний.

### Коммуникация с руководством

- **Демонстрация издержек**: расчёт потерь времени на исправление ошибок и сравнение с затратами на профилактику.
- **Акцент на ROI**: например, снижение частоты инцидентов на 60% после рефакторинга увеличивает доступность продукта[^5].
- **Пилотные проекты**: постепенное улучшение отдельных модулей с измерением влияния на скорость разработки.


### Организационные меры

- **Обучение**: курсы по чистой архитектуре и рефакторингу, обязательные для всей команды.
- **Геймификация**: система бонусов за сокращение технического долга или улучшение метрик.
- **Ротация задач**: предотвращение монополизации критически важных компонентов говнокодерами.

---

## Заключение

Говнокодеры представляют системную угрозу для IT-проектов, маскируя свою некомпетентность под ложными аргументами оперативности. Их деятельность приводит к долгосрочным финансовым и репутационным рискам, разрушая командную динамику и архитектурную целостность. Ключом к решению проблемы является комбинация технических (внедрение метрик, код-ревью) и организационных мер (обучение, ротация), подкреплённая прозрачной коммуникацией с руководством на языке бизнес-показателей. Как отмечает Никита Ефимов в подкасте Make Sense, борьба с культурой говнокодинга требует пересмотра самого подхода к оценке успеха — не через количество строк кода, а через устойчивость и адаптивность системы[^4].

<div style="text-align: center">⁂</div>

[^1]: https://habr.com/ru/articles/66973/

[^2]: https://infostart.ru/1c/articles/1678484/

[^3]: https://habr.com/ru/articles/670700/

[^4]: https://sense23.com/podcast/make-sense-161-o-protsesse-i-komandah-product-discovery-balanse-run-i-change-i-time-to-knowledge-s-nikitoj-efimovym

[^5]: https://news.ycombinator.com/item?id=29919950

[^6]: https://codefinity.com/blog/13-Bad-Practices-in-Python-Coding

[^7]: https://en.wikipedia.org/wiki/Cowboy_coding

[^8]: https://www.sostav.ru/publication/digital-geeks-54020.html

[^9]: https://news.ycombinator.com/item?id=6333424

[^10]: https://news.ycombinator.com/item?id=9477301

[^11]: https://foxhound-lj.livejournal.com/469298.html

[^12]: https://streithahn.livejournal.com/182296.html

[^13]: https://habr.com/ru/companies/hygger/articles/354800/

[^14]: https://habr.com/ru/articles/419231/

[^15]: https://qna.habr.com/q/429650.

[^16]: https://habr.com/ru/articles/66973/comments/

[^17]: https://qna.habr.com/q/429650

[^18]: https://pikabu.ru/story/obektnoorientirovannoe_programmirovanie_dlya_govnokoderov_9438347

[^19]: https://www.cyclic.sh/posts/write-shitty-code

[^20]: https://tsh.io/blog/bad-coding-practices/

[^21]: https://www.youtube.com/watch?v=wO1QScIDZbk

[^22]: https://neolurk.org/wiki/Быдлокодер

[^23]: https://vc.ru/legal/1745855-podrazdelenie-oracle-v-rossii-podalo-iski-na-1729-mln-rublei-k-kompaniyam-iz-za-kotoryh-ono-obankrotilos?comment=8355530

[^24]: https://dtf.ru/1704208-vse-chto-nuzhno-znat-pro-vash-314zdyuchii-chatgpt-pridumal-nesushestvuyushie-mody-dal-levye-ssylki-i-glazom-ne-morgnul?comment=23712582

[^25]: https://news.ycombinator.com/item?id=28543236

[^26]: https://codingcraftsman.wordpress.com/2023/03/13/how-to-have-terrible-code-reviews/

[^27]: https://2ch.hk/vg/arch/2021-02-26/res/36278899.html

[^28]: https://habr.com/ru/articles/419231/comments/

[^29]: https://www.reddit.com/r/dotnet/comments/1b134h2/im_tired_of_working_with_bad_code/

[^30]: https://stackoverflow.com/questions/1575323/how-to-deal-with-seniors-bad-coding-style-practices

[^31]: https://todogood.com/quickwins

[^32]: https://dzen.ru/a/Xw_sSskMf24q1jTC

[^33]: https://softwareengineering.stackexchange.com/questions/1338/worst-coding-standard-youve-ever-had-to-follow

[^34]: https://softwareengineering.stackexchange.com/questions/238413/how-to-deal-with-team-members-writing-bad-code

