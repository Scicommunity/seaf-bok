
# SEAF.KNOWLEDGE

---
## Часть 1. Что такое управление знаниями

Что такое управление знаниями для создания архитектурного фреймворка


---
### Что такое знание


   >    **Знание — это зафиксированная информация, полученная различными путями (через опыт, обучение, наблюдение, размышление, общение и т.п.) и которая может быть использована для прогнозирования, объяснения, принятия решений или управления.**
   
---
###  Знания на входе ДКА ДЗО

![[knowledgeformsin.svg]]

---
###  Знания на выходе ДКА ДЗО

![[knowledgeformsout.svg]]

---
###  Стейкхолдеры (1)

Стейкхолдер SEAF - заинтересованное лицо в получении полезных для себя знаний из SEAF

![[stakeholders.svg]]

---
###  Стейкхолдеры (2)


| ID  | Область             | Аналитик                                     | Разработчик                                     | Архитектор                          | Владелец, управленец и их команды |
| --- | ------------------- | -------------------------------------------- | ----------------------------------------------- | ----------------------------------- | --------------------------------- |
| 1   | ДКА ДЗО             | -                                            | разработчик реф.  инструментов упр. арх. Группы | курирующий архитектор               | владелец процесса, инструмента    |
| 2   | ДЗО                 | бизнес-/системный/продуктовый аналитик ДЗО   | Разработчик продукта/ сервиса/АС ДЗО            | Архитектор продукта/ сервиса/АС ДЗО | Владелец продукта/ сервиса/АС ДЗО |
| 3   | Внешняя организация | Аналогично ДЗО                               | Аналогично ДЗО                                  | Аналогично ДЗО                      | Аналогично ДЗО                    |
| 4   | ДКА и Банк          | бизнес-/системный/продуктовый аналитик Банка | TBD                                             | TBD                                 | TBD                               |
| 5   | (?)                 |                                              |                                                 |                                     |                                   |

Для разнесения: тут где-то должны быть КБ? ДТН? Кого не хватает? 


---
###  Стейкхолдеры (список)

Целевая аудитория SEAF:

- бизнес-аналитики

- системные аналитики

- любые продуктовые команды, начинающие создавать и развивающие свои цифровые продукты с использованием open-source - решений

- системные и корпоративные архитекторы

- владельцы, архитекторы и менеджеры продуктов

- разработчики продуктов

- любые участники архитектурной функции организации, в том числе ответственные за организацию и результаты архитектурной функции

- руководители, в чьей зоне ответственности находится создание продуктов организации.

---
### Ценностное предложение для аналитиков (1 из 8)

**Условное (краткое) наименование: «Документация рядом с кодом»**

Ценность: документация цифрового продукта (АС или сервиса) консистентно и непрерывно развивается вместе с исходным кодом продукта

Преимущества:
- Уменьшение противоречий между документацией и реализацией (что написано в документе - то и в реальном ландшафте/системе/решении). Как достичь: (1) отделить документы от контента (данных), из которого документы формируются (2) данные генерировать из инфраструктуры и кода (увеличивать достоверность)
- Автоматизированная сборка и публикация документации, снижающая вероятность устаревания информации и повышающая T2M выпуска документов. Как достичь: (3) автоматизировать генерацию документа из данных (шаблонизаторы, генераторы)
- Повышение прозрачности продуктов, проектов, ИТ-решений за счет того, что все изменения отражаются как в коде, так и в документации. Как достичь: (4) автоматизировать генерацию архитектурных данных из кода (как пример - deepwiki) (5) автоматизировать генерацию кода из архитектурных данных


---
### Ценностное предложение для аналитиков (2 из 8)

**Условное (краткое) наименование: «Требования рядом с кодом»**

Ценность: требования (как правило, в форме проектных документов) напрямую связаны (т.е. явно трассируются) с архитектурными компонентами создаваемого продукта в архитектурных данных, связанных, в свою очередь, с исходным кодом

Преимущества:
- Ясная трассировка требований до реальных компонентов продуктов. Как достичь: (6) Модель управления архитектурой должна содержать требования и необходимые связи (7) ??Научиться хранить связь между компонентом в архитектурных данных и компонентом продукта
- Управление версиями требований (данных) благодаря их прямой связи с версиями кода Как достичь: (8) использовать СКВ GIT
- Снижение рисков несоответствия между требованиями и реализацией Как достичь: (9) научиться валидировать требования

---
### Ценностное предложение для аналитиков (3 из 8)

**«Основа любой сложной системы и системного анализа - данные (код) архитектуры»:**

Ценность: архитектурный код, написанный аналитиком при проектировании, становится фундаментальной частью продукта или системы

Преимущества:
- Обеспечивает единство языка для аналитиков, архитекторов, разработчиков для описания на всех этапах разработки. Как достичь: (10) создать глоссарий SEAF
- Снижает страх перед написанием архитектурного кода у аналитиков благодаря поддержке коллег и понятным методам работы Как достичь: (11) Научиться решать аналитические задачи управляя архкодом
- Код архитектуры – ключевой артефакт, вокруг которого фокусируются интересы аналитиков, архитекторов и разработчиков. Аналитик, работая с ним, вовлекается в полный цикл производства Как достичь: (11) Научиться решать аналитические задачи управляя архкодом

---
### Ценностное предложение для аналитиков (4 из 8)

**«Актуальность документации на работающий продукт»** (в том числе долгосрочная)

Ценность: в отличие от традиционных подходов, где документы актуальны только на момент создания системы, артефакты SEAF остаются востребованными на протяжении всего жизненного цикла продукта.

Преимущества:
- Обеспечивает непрерывное участие аналитика в процессе эксплуатации, сопровождения и модернизации системы
- Позволяет поддерживать актуальность архитектурного кода и данных даже после первоначального запуска продукта

---
### Ценностное предложение (5 из 8)

**«Управление развитием продукта с использованием Digital ADR»:**

Ценность: использование цифровых записей развития архитектуры (Digital ADR) как части метаданных, интегрированных с кодовой базой продукта.

Преимущества:
- Обеспечивает прозрачность изменений в архитектуре системы за счет прямой связи с исходным кодом
- Позволяет верифицировать исполняемый код относительно архитектурных решений
- Упрощает отслеживание эволюции проекта на всех этапах разработки
- Упрощает поиск и анализ информации о системе на любом этапе ее жизненного цикла
- Позволяет быстро адаптироваться к изменениям в проектных требованиях или технологических решениях

---
### Ценностное предложение (6 из 8)
**«Коллаборация со всей вертикалью управления продуктами»:**

Ценность: стимуляция эффективного взаимодействия между аналитиками, архитекторами и владельцами продукта или системы.

Преимущества:
- Повышает качество коммуникации за счет использования общих цифровых инструментов для описания развития архитектуры
- Снижает риск недопонимания или несоответствия в требованиях благодаря единому формату документации
- Упрощает коммуникацию и сотрудничество между аналитиками, архитекторами и разработчиками за счет использования общего формата описания системы, что повышает качество конечного продукта

---
### Ценностное предложение для аналитиков (7 из 8)
**«Повышение востребованности и значимости» аналитической функции:**

Ценность: результаты работы аналитика напрямую используются разработчиками и архитекторами, что увеличивает его значимость в сквозном процессе производства информационных систем или цифровых продуктов.

Преимущества:
- Увеличивается влияние аналитика на конечный продукт за счет прямой связи между его работой и кодом
- Повышается признание роли аналитика в команде благодаря сохранению его имени в аннотациях к коду

---
### Ценностное предложение для аналитиков (8 из 8)
**«Роль со-создателя системы» для аналитика:**

Ценность: аналитики из составителей проектной документации становятся полноценными соучастниками создания продукта.

Преимущества:

- Расширяются возможности влияния на процесс производства за счет прямого участия в разработке архитектуры и метаданных
- Увеличивается вовлеченность в управление изменениями и последующее развитие продукта (рефакторинг, импортозамещение, миграция)

В парадигме SEAF предоставляется свобода творчества для аналитика: есть свое пространство для выражения своих идей через написание кода, описывающего структуру программы или системы.

Благодаря этому подходу аналитики и архитекторы сходятся в работе над одним артефактом - кодом архитектуры продукта, из которого мы можем получить любой архитектурный артефакт для стейкхолдера Продукта и описание работающих приложений или систем.

![Рис. 1. Структура кодовой базы Продукта](/ProductCode.png)

Рис. 1. Структура кодовой базы Продукта

---
### "Машинка" для создания архитектурного фреймворка

![[howtocreateframework.svg]]

---
### "Машинка" производства знаний

![[knowledgemachine.svg]]

Знание отражает **полезный для использования результат познания**.

---
### Немного юмора

Исторический контекст: на заре создания SEAF заинтересованные люди часто задавали вопрос: существует ли SEAF и приносит ли он пользу? Часто ответ был с объяснением, что "мы рассмотрели там такие-то вопросы, включили в репозитории подходы к решению". После чего часто пользователи говорили: ну это не моя непосредственная задача, поэтому для меня наверно он еще не нужен...

Почему >90% пользователей TOGAF начинают считать TOGAF "существующим" и "полезным"?

Они делают такой вывод, скачав "Evaluation copy", положив его в свой архив файлов, открыв его и увидев в структуре оглавления знакомые слова из задач, с которыми ИТ-архитекторы, аналитики сталкиваются в своей работе. **Не извлекая при этом из TOGAF никакой практической пользы.**

---
###  Документация архитектурного фреймворка

**- это классифицированное, структурированное, формализованное знание, представленное в установленных для документации форматах (документах) и предназначенное для управления архитектурой сложных систем (например, ИТ-решений, предприятий или их групп).**

По тому, как подготовлена базовая (самая общая, основная) документация фреймворка большинство будет делать вывод о полезности, удобстве и т.п. фреймворка. 

Она занимает центральное место в управлении знаниями, обеспечивая стандартизацию, преемственность и коммуникацию между всеми участниками архитектурного процесса.

---
### Какими свойствами должна обладать система управления знаниями SEAF?


**Система управления знаниями (СУЗ) в архитектурном фреймворке** должна обладать рядом ключевых свойств, обеспечивающих её эффективность, гибкость и соответствие современным требованиям к архитектуре предприятий и цифровой трансформации.

---
### Основные свойства

  
- **Поддержка полного жизненного цикла знаний**

    - Система должна обеспечивать формирование, хранение, структурирование, поиск, распространение, обсуждение, оценку и обновление знаний в рамках архитектурного фреймворка.

- **Гибкость и масштабируемость**

    - Архитектура должна быть модульной, поддерживать слабую связанность компонентов, легко расширяться за счёт внедрения новых модулей и сервисов, а также адаптироваться к изменяющимся требованиям[^2][^4].

- **Интеграция и совместимость**

    - Система должна быть способна интегрироваться с другими корпоративными и внешними системами, обеспечивать совместимость и обмен знаниями между различными платформами и организациями.

- **Многообразие форм представления знаний**

    - Поддержка различных формализованных и неформализованных представлений знаний: текст, аудио, видео, графика, модели, электронные документы и т.д.

- **Ролевое и разграниченное управление доступом**

    - Наличие гибкой системы управления ролями, правами и доступом пользователей к различным доменам знаний и функциям системы.

- **Инструменты для совместной работы**

    - Возможность группового обсуждения, коллективного редактирования, комментирования, ведения истории изменений и версионности знаний.

- **Информационная безопасность**

    - Защита знаний от несанкционированного доступа, обеспечение целостности и конфиденциальности данных, соответствие стандартам безопасности.

- **Управление качеством и оценка знаний**

    - Возможность оценки и ранжирования знаний пользователями, мониторинг актуальности и релевантности информации.

- **Управление метаданными и онтологиями**

    - Использование стандартов структурирования информации (например, XML, RDF), поддержка онтологий для семантической обработки и интероперабельности знаний.

- **Удобство использования и пользовательский опыт**

    - Интуитивно понятный интерфейс, поддержка уведомлений, персонализация и настройка рабочих пространств для разных категорий пользователей.

- **Мониторинг, поддержка и развитие**

    - Механизмы мониторинга состояния системы, обновления, поддержки и развития функционала в соответствии с изменяющимися бизнес- и технологическими требованиями.

Разнести мысли:

1. Периодически, ритмично поставлять документацию фреймворка для стейкхолдеров, позволяющую им оценивать применимость подхода для своих задач и начать его применять
2. Оценивать как управляется/распространяется знание
3. Если руководство требует придумывать прорывные идеи и дизрапты в какой-то области, то как управление знаниями в SEAF помогает это знание формировать? Какие свойства надо учесть чтобы такое знание формировать? 
4. Уметь собирать и проверять какие-либо гипотезы, поддерживать формы коллаборации и брейнсторма?

---
### Примерная структура свойств в таблице

| Свойство                    | Описание                                                             |
| --------------------------- | -------------------------------------------------------------------- |
| Жизненный цикл знаний       | Формирование, хранение, поиск, распространение, обновление           |
| Гибкость и масштабируемость | Модульность, расширяемость, адаптация к изменениям                   |
| Интеграция и совместимость  | Взаимодействие с внешними и внутренними системами                    |
| Многообразие форм знаний    | Текст, аудио, видео, графика, модели, документы                      |
| Управление доступом         | Ролевое разграничение, права пользователей                           |
| Совместная работа           | Групповое обсуждение, коллективное редактирование, история изменений |
| Информационная безопасность | Защита данных, соответствие стандартам безопасности                  |
| Оценка и качество знаний    | Оценивание, мониторинг актуальности, релевантность                   |
| Метаданные и онтологии      | Стандарты структурирования, поддержка онтологий                      |
| Удобство использования      | Интерфейс, уведомления, персонализация                               |
| Мониторинг и поддержка      | Отслеживание состояния, обновления, развитие                         |
|                             |                                                                      |

---

## Часть 2. Целевой образ управления знаниями в SEAF

Что такое управление знаниями для создания архитектурного фреймворка


---
###  **Пайплайн производства документации **

![[docspipeline.svg]]

---
###  Сценарии (кейсы) управления знаниями





---
## Приложения

---
### Данные и документы SEAF в закрытых контурах
![[Conflvls.svg]]

---
### Классификация материалов SEAF по назначению

![[docsclassification.svg]]

---
### Классификация

Знания классифицируют по:
1. По степени формализованности
2. По функциональному назначению
3. Формату
4. Месту хранения:
	- "Знание как конфлюенс"
	- Знание "как код" в GIT-репозитории
---
### Требования к документации фреймворка
#### 1. **Структурная организованность**
 
- **Использование шаблонов** для каждого типа документа с разделом назначения документа и реквизитами

- **Иерархическая организация контента**: см. структуру документации в следующих разделах

- **Разделение на логические блоки**: например, бизнес-требования, функциональные спецификации, технические ограничения
 
  #### 2. **Семантическая точность**

  - **Однозначность терминов** с глоссариями и ссылками на предметные области. Не нужно использовать все 500 терминов глоссария

- **Исключение субъективных формулировок** ("удобный интерфейс" → "время отклика ≤ 2 сек")

- **Контекстная завершённость** (полное описание условий применения требований)

#### 3. **Проверяемость и измеримость**

- **Критерии приемки** для каждого требования с указанием методов верификации (тесты, инспекции...)

- **Метрики качества**: (полнота охвата функций), точность соответствия целям

- **Трассируемость изменений** через версионность и систему ссылок


#### 4. **Технологическая совместимость**
  
- **Поддержка machine-readable форматов** (yaml, JSON, XML-схемы, UML)

- **Автоматизированная генерация документации** из исходного кода и моделей

#### 5. **Процессуальные требования**
 
- **Этапность формализации**: сбор → анализ → спецификация → валидация

- **Обязательные рецензирование и согласование** с ключевыми стейкхолдерами[^2][^9]

- **Жёсткий контроль версий** с историей изменений
 
Для ИТ-продуктов критически важна **двусторонняя связь документации с реализацией** – требования должны отражаться в:
 
- Тестовых сценариях (на 100% покрытие функций)

- Архитектурных решениях (соответствие нефункциональным требованиям)

- Пользовательских интерфейсах (валидация через прототипы)


---
###### Измерение новизны знаний в SEAF

![[dimensionofknowledgenewness.svg]]

---
###### Измерение коллективности знаний в SEAF

![[dimensionofknowledgecollectiveness.svg]]

---
###### Измерение конкретности знаний в SEAF

![[dimentionofknowledgeconcrete.svg]]

---


###### Измерения управления знаниями SEAF


![[Knowledgekpi.svg]]

Принцип: 
> Создание знаний необходимо измерять: по степени новизны, по степени распределенности, по степени определенности.

---
#####  Форматы документации фреймворка и обучающих материалов

Форматы документации:
- pdf - файлы для скачивания и изучения
- HTML - страницы с навигацией, медиаконтентом

Форматы обучающих материалов:
- **SCORM**. Формат задаёт определённые правила разработки курсов, которые понимают многие платформы. Готовые учебные материалы упаковывают в SCORM-пакет — это стандартный zip-архив.
- **XHTML или HTML5** Некоторые инструменты для создания интерактивного контента позволяют генерировать такие файлы, создавать веб-страницы с удобной навигацией, включая изображения, текст, мультимедийные клипы и интерактивные действия.

#####  Что такое управление знаниями для задачи создания архитектурного фреймворка

##### Знаниями о чем нужно управлять?

---

##### Общие принципы управления знаниями SEAF
1. Знания архитектурного фреймворка = совокупность знаний всех кто вовлечен в создание или использование этого фреймворка
2. Управление знаниями и управление инновациями (генерация и проверка идей/гипотез) - это одна область управления
3. Создание знаний необходимо измерять: по степени новизны, по степени распределенности, по степени определенности.
4. Создание знаний - это и есть производственный процесс при создании фреймворка
5. Разработку знаний нужно направлять а) с учетом структуры создаваемого знания б) с учетом интересов потребителей
---
##### Чьими знаниями мы хотим управлять? Целевая аудитория УЗ архитектурного фреймворка



---

##### Какие задачи обычно решаются при управлении знаниями?

--- 
## Апокрифы

---
### Возможности docs as code in DocHub

![[docsascodeindochub.svg]]

---
### Часть 2.  Допматериалы Управление знаниями в контексте SEAF

---
##### Специфика УЗ SEAF, где SEAF - все, чем занимается ДКА ДЗО

---

##### 4 квадранта SEAF и причины выделения управления знаниями
(см. презентацию в pptx)

---
##### Инвентаризация накопленных знаний

В таблице: область знаний, место хранения. Какие сущности/ куски знаний - надо поименовать

---
---

##### Открытые гештальты / вопросы / извлеченные уроки

Осознанные на текущий момент
Какие боли мы хотим полечить (возможно отделить симптомы от проблем)

---
##### Возникновение потребности перевода УЗ SEAF на новый уровень в имеющихся ресурсах

---
#####  Почему настало время для конкретно нашей ситуации начать системно управлять знаниями?

---



##### Области накопленного знания ДКА ДЗО

---
##### Что мы НЕ рассматриваем в рамках управления знаниями SEAF

---

##### Какими целями руководствуемся при УЗ?

---
##### Почему нам надо и какие задачи хотим научиться решать в рамках УЗ в ДКА ДЗО

--- 

### Часть 3. Допматериалы

---
##### Пример консорциума TM Forum

Цели
Причина релевантности SEAF:

---

##### Пример консорциума OpenGroup

Цели
Причина релевантности SEAF:

---
##### Пример ИТ-проекта Kubernetes

---
##### Пример ИТ-проекта Docker
---
##### Пример ИТ-проекта OZON
---
#####  Примеры управления документацией в GitHub

---
#####  Пример управления документацией сообщества

Проблема: распространение документации, записей мероприятий сообществ в виде анонсов событий, видеозаписей мероприятий, презентаций в формате pptx - моветон.
А какие современные методы есть?


---

#####  Пример проекта DeepWiKi

---

#####  Пример FixGPT

---



Все вопросы по управлению знаниями SEAF

![[Вопросы к рассмотрению (разобрать).svg]]

---
Предложение

Продолжать подготовку к выступлениям на конференциях по вопросу управления документированием для аудитории в лице бизнес- и системных аналитиков.

Почему продолжить? Потому что изначально тезисы для конференции Flow были подготовлены совместно Д. Порошиным, потом прервались для решения задач легимитизации SEAF и стабилизации материалов. 


---
#####  Амбициозный DOD "столпа" SEAF.Knowledge

1. Ясно ответить на 10 вопросов первого порядка по управлению знаниями в SEAF
2. Выпуск первой версии документации фреймворка SEAF (удовлетворяющего всем требованиям)
3. Разблокировка и подготовка к докладу на конференции по темам управления знаниями/документами SEAF совместно с Порошиным(?) Пример - Flow и набор представленных ценностей для бизнес- и системных аналитиков. Нужны POC, нужны кейсы для обучения. Включая кейс подготовки презентаций.
4. На примере построения "презентаций как код" запустить добровольную практику отказа Сбера от практики "слайдостроительства" и "проектирования архитектуры в крупную клетку" (без привязки и оглядки на архитектуру решений и кода). 
5. Увеличить креативность участников создания SEAF (и так, чтобы это не вызывало скептической улыбки)
6. Опробовать быстрое создание материалов обучения
7. Сформировать ясный набор требований к референсным инструментам
8. Представить MVP нового инструмента, который спроектирован "с нуля" на основе принципов SEAF gen 2
9. 
10. 



---
## Что не рассматривается на встречах


> **Правило 1. Когда обсуждаем концепцию, мы не говорим об инструментах / имплементации. Примеры**


> **Правило 2. Мы не говорим о содержании знаний/документов. Примеры**


> **Правило 3. Мы пока обсуждаем рабочие (не финальные) материалы концепции и презентации. Брейнсторм, новые идеи - приветствуются**