* Вопрос 2: Как оценка производительности связана с командой ...?
    * RQ 2.1: Что факторы, влияющие на производительность, могут рассказать о команде разработчиков?
    * RQ 2.2: Какие факторы имеют больший вес в описании команды?
    * RQ 2.3: Как сопоставить метрики с командой ...?

    Воспросы:

    1 - Что такое производительность команды разработчиков ПО?
    2 - какие факторы влияют на производительность команды разработки ПО?
    3 - как можно оценить производительность комнады разработчиков ПО?

Производительность команды в сфере разработки программного обеспечения является одним из важнейших аспектов проектов IT индустрии, так как производительность команды связывает технические, экономические и социальные факторы которые напрямую влияют на трудовые и денежные затраты для реализации IT проекта.  (1)
Такое сочетание множества сложных факторов и большая цена ошибки делает понятие производительности команды разработки очень интересным и многогранным объектом для исследования.
Тема производительности команд разработки ПО стала особенно актуальна после пандемии COVID-19, когда множество разработчиков были вынуждены работать из дома и привычные процессы взаимодействий внутри команды нуждались в срочных изменениях. (2)
В рамках нашего тезиса под производительностью мы понимаем следующее: In software development, developer productivity refers to a team's ability to achieve outlined business objectives through developing, improving, and maintaining software. (3)

Для возможности влиять на производительность команды, важно определить факторы, напрямую определяющие производительность. В 2021 году на конференции ACM Queue команда исследователей из Microsoft Research, GitHub и д.р. предложила фреймворк под названием SPACE. Этот фреймворк определяет факторы производительности команд разработки программного обеспечения. SPACE представляет собой многомерный подход к оценке продуктивности разработчиков, который выходит за рамки традиционных метрик и учитывает не только технические, но и социальные аспекты работы команды.

- Satisfaction : Степень удовлетворенности разработчиков своей работой оказывает значительное влияние на их мотивацию и общее качество выполнения задач. Высокий уровень удовлетворенности может способствовать росту продуктивности.

- Performance: Это традиционный критерий, который включает как количественные показатели (например, число завершенных задач или функций), так и качество выполненной работы.

- Activity: Данный параметр оценивает уровень активности разработчиков с помощью таких метрик, как число коммитов или время, затраченное на программирование. Это позволяет оценить вовлеченность команды.

- Communication and Collaboration: Эффективное взаимодействие внутри команды имеет решающее значение для успешной разработки программного обеспечения. Этот параметр охватывает качество коммуникации между членами команды.

- Efficiency and Flow: Данный показатель измеряет, насколько эффективно команда использует свои ресурсы для достижения поставленных целей. Поток описывает состояние максимальной концентрации разработчиков на выполнении задач.
(4)

Метрики платформы SPACE помогают командам разработчиков программного обеспечения лучше понимать продуктивность различных аспектов своей работы.
Эти показатели не только измеряют производительность, но также фокусируются на удовлетворенности сотрудников и качестве взаимодействия в команде, помогая создать более эффективную и гармоничную рабочую среду. (4)

| **SPACE**                | **Metric type**    | **Metric**                                                                                      |
|------------------------------|---------------------|--------------------------------------------------------------------------------------------------|
| **Satisfaction**             | Individual        | Developer satisfaction. 
||Individual|Retention 
||Individual|Satisfaction with code reviews assigned 
||Individual|Perception of code reviews                                                     |
|                              | Team or Group           | Developer satisfaction
||Team or Group|Retention
||System| Satisfaction with engineering system (e.g., CI/CD pipeline)                                                  |
| **Performance**              | Individual       | Code review velocity                                                                    |
|                              | Team or Group           | Code review velocity 
||Team or Group |Story points shipped                                     |
|                              | System      | Code review velocity
||System|Code review (acceptance rate)
||System|Customer satisfaction
||System|Reliability (uptime)                              |
| **Activity**                 | Individual       | Number of code reviews completed
||Individual|Coding time
||Individual|Commits
||Individual|Lines of code                                                                    |
|                              | Team or Group           | Story points completed
||System|Frequency of deployments|                                                          |
| **Communication and Collaboration** | Individual   | Code review score (quality or thoughtfulness)
||Individual|PR merge times
||Individual|Quality of meetings†
||Individual|Knowledge sharing, discoverability (quality of documentation)                                                              |
|                              | Team or Group           | PR merge times
||Team or Group   |Quality of meetings
||Team or Group   |Knowledge sharing or discoverability (quality of documentation) 
||System|Knowledge sharing, discoverability (quality of documentation)|            |
| **Efficiency and Flow**     | Individual       | Code review timing
||Individual|Productivity perception 
||Individual|Lack of interruptions                                                                          |
|                              | Team or Group           | Code review timing
||Team or Group|Handoffs                                                             |
|                              | System      | Code review timing
||System|Velocity/flow through the system                  |






1: Duarte, C.H.C. Software Productivity in Practice: A SystematicMapping Study. Software 2022, 1,164–214. https://doi.org/10.3390/software1020008

2: Ralph, P., et al. 2020. Pandemic programming: How Covid-19 affects software developers and how their organizations can help. Empirical Software Engineering25(6), 4927-4961; https://www.researchgate.net/publication/344342621_Pandemic_programming_How_COVID-19_affects_software_developers_and_how_their_organizations_can_help.

3: Zenhub. "Developer Productivity Management: A Complete Guide." Accessed November 6, 2024. https://www.zenhub.com/guides/developer-productivity.

4: Nicole Forsgren, Margaret-Anne Storey, Chandra Maddila, Thomas Zimmermann, Brian Houck, and Jenna Butler. 2021. The SPACE of Developer Productivity: There's more to it than you think. Queue 19, 1, Pages 10 (January-February 2021), 29 pages. https://doi.org/10.1145/3454122.3454124
