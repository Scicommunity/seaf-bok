---
title: Как разметить статью или исходный код
weight: 9
bookCollapseSection: false
bookFlatSection: true
bookToc: false
# bookHidden: false
bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
tags:
  - #seaf_bok

---

## Требования лицензии и авторского права при публикации SEAF

SEAF публикуется под лицензией Apache 2.0.

С целью удовлетворения требований авторского права соавторов разработки SEAF, лицензии apache-2.0, интересов правообладателей, - при публикации репозиториев
необходимо предусмотреть и актуализировать в процессе доработок:

1.  Файл notice по образцу:

```
  SEAF CORE

  Copyright (C) 2023 Sber

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this product except in compliance with the License.
  You may obtain a copy of the License at
          http://www.apache.org/licenses/LICENSE-2.0
  
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
```

2. Файл contributors по образцу, где нужно перечислить файлы, в
которые нельзя добавить комментарий (две последние строки должны
присутствовать):

```
### Creator SEAFTeam

# Contributors

#### Vladislav Markin, Sber
* core modules
* vue components
* project configuration
* ./.eslintrc.json - 2022 - contributor
* authentication
* metamodel
* ./public/metamodel/dochub/entities/contexts/plantuml.yaml - 2023 - contributor
* ./public/metamodel/dochub/entities/documents/base.yaml - 2023 - contributor
* ./public/metamodel/dochub/entities/contexts/smartants.yaml - 2023 - contributor
* documentation
* ./public/documentation/docs/manual/jsonata.md - 2023 - contributor
* ./public/documentation/docs/manual/docs/charts.md - 2023 - maintainer, contributor
* ./public/documentation/docs/manual/docs/smartants.md - 2023 - contributor
* ./public/documentation/docs/manual/entities/entities.md - 2023 - contributor

#### Nikolay Temnyakov, Sber
* core modules
* vue components
* authentication and role model
* tests
* ./tests/global/__mocks__/* - 2023 - contributor
* documentation
* ./public/documentation/docs/manual/entities/rules.md - 2024 - maintainer, contributor

#### Maxim Sitnikov, Sber
* assets
* ./src/assets/c4model_dsl.txt - 2021 - maintainer, contributor
* ./src/assets/sber_dsl.txt - 2021 - maintainer, contributor

*Changes that are not directly reflected in the code are specifically noted here.
For additional contributors and details, please see sources and the Git commit history.*
```

3. В каждый файл репозитория (в который технически возможно
добавление комментария), добавляется комментарий по образцу:
```
/*

Copyright (C) 2023 Sber

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
        http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Maintainers:
    scicommunity <kia@sci.community>
    ruDmitry <...>

Contributors:
    Vladislav Markin, Sber – 2023 - Bug fixes, Gravity points enhancements
    Vladislav Markin, Sber – 2023 - Added background and title attributes
    Vlad Nefedov, Sber – 2023 - Bug fixes, fullscreen mode
*/
```

Комментарии:

1.  Maintainer -- тот, кто поддерживает / проводит ревью изменений
    данного файла, кому писать вопросы, запросы на ревью. Чаще всего это
    создатель файла. Если человек вышел из разработки SEAF (создал файл,
    но не поддерживает его и не является ревьюером), то вместо него
    указывается преемник(и), осуществляющие код ревью.

2.  Contributor -- автор любой строки кода или данных независимо от
    того, является ли он в настоящее время контрибьютором в SEAF.
    Отражает факт наличия вклада в развитие SEAF на каком-либо этапе
    развития.

3.  По образцу , помимо года, желательно указывать изменения (или
    характер изменений), сделанных контрибьютором.
