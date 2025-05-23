# Архитектурные объекты слоя "Информационная архитектура"





## Состав информационной архитектуры
Информационная архитектура в текущем релизе состоит из базовых сущностей:
- Информационный актив
- Бизнес-объект
- Объект данных

**Информационный актив** - информация, данные, документы, являющиеся активом компании и используемые в бизнес-процессах управления или при предложении, формировании, предоставлении потребителям продуктов или услуг.

**Бизнес-объект** - информационный объект, которым оперируют бизнес-процесссы компании при формировании продуктов, например, **клиент**, **исполнитель**, **услуга**.

**Объект-данных** - часть бизнес-объекта, обрабатываемая в автоматизированной системе и/или интеграции, например, **ФИО**, **адрес**, **номер телефона**.

| Наименование              | Идентификатор сущности  |
|---------------------------|-------------------------|
| **Информационный актив** | seaf.ia.info_assets |
| **Бизнес-объект**         | seaf.ia.business_object |
| **Объект данных**         | seaf.ia.data_object     |


## Наборы атрибутов сущностей
**Информационный актив**

| Атрибут      | Описание                                                                      |
|--------------|-------------------------------------------------------------------------------|
| **title**    | Наименование                                                                  |
| **name**     | Полное Наименование                                                           |
| **version**  | Версия информационного актива                                                 |
| **status**   | Статус реализации (одно из значений из списка)                                | 
| **requirements**   | Требования (одно из значений из списка)                                       | 
| **process**  | Ссылка на бизнес-процесс (**seaf.ba.processes**) в котором используется актив |
| **comments** | Дополнительная текстовая информация для описания объекта                      |
--

**Бизнес-объект**

| Атрибут  | Описание                                                                          |
|----------|-----------------------------------------------------------------------------------|
| **title**    | Наименование                                                                      |
| **status**   | Статус реализации (одно из значений из списка)                                    | 
| **process**  | Ссылка на бизнес-процесс (**seaf.ba.processes**) в котором используется бизнес-объект |
| **comments** | Дополнительная текстовая информация для описания объекта                          |
--
        
**Объект данных**

| Атрибут         | Описание                                                                                                                                        |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **title**           | Наименование                                                                                                                                    |
| **category**        | Категория или тип данных (значение из списка, список расширяемый)                                                                               |
| **status**          | Статус реализации (одно из значений из списка)                                                                                                  | 
| **business_object** | Ссылка на бизнес-объект (**seaf.ia.business_object**) частью которого является объект данных (например ФИО является частью бизнес-объекта Клиент) |
| **master_system**   | Мастер-система (прикладной компонент) объекта данных                                                                                            |
| **comments**        | Дополнительная текстовая информация для описания объекта                                                                                        |

## Примеры сущностей

**Бизнес-объект**
```yaml
seaf.ia.business_objects:
    sber.berezka.business_objects.client:
        title: Клиент
        status: Используется
        processes:
            - sber.berezak.ba.processes.process_1
```

**Объект данных**
```yaml
seaf.ia.data_objects:
    sber.berezka.data_objects.client_name:
        title: ФИО Клиента
        status: Используется
        business_object: sber.berezka.business_objects.client
        category: Перс.данные
        master_system: sber.berezka.components.home_cinema
```