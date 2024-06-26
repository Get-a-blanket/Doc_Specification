---
csl: gost-r-7-0-5-2008-numeric-iaa.csl
bibliography: demo.bib
...

# Введение

Данное техническое задание определяет цель, структуру, свойства и методы разработки программного продукта для обеспечения работы системы вендинговых аппаратов для сдачи пледов в краткосрочную аренду. 

Программный продукт позволяет предоставить пледы, которые помогут согреться в холодную погоду без изменения планов прогулки. Коммерческий проект ориентируется как на B2C (приоритетно), так и на B2B с планами на сотрудничество с парками и кафе. Для тех, кто хочет провести время на свежем воздухе, предлагается решение проблемы – посуточная аренда пледов через приложение и вендинговые автоматы, не приобретая пледы, которые будут использоваться однократно. С помощью данного проекта проблема холода во время прогулки может быть решена на время, так как пледы обогревают на несколько часов, позволяя продолжить прогулку. Современные люди ценят удобство и мгновенный доступ к услугам. Развитие вендинговых аппаратов для посуточной аренды пледов соответствует этим потребностям, предоставляя быстрое и легкодоступное решение для тех, кто желает комфортно провести время на улице. Не менее важно влияние проекта на социальную активность. Поощряя людей проводить больше времени на улице, продукт способствует развитию здоровья и общего состояния. Проект также ориентирован на местный туризм: парки Москвы являются неотъемлемой частью туристической зоны города, поэтому проект имеет потенциал поддержки местной экономики и привлечения туристов.

# Основание разработки 

Перечень документов, на основании которых создаётся ИС:

 - Положение о государственной итоговой аттестации студентов образовательных программ высшего образования -– программ бакалавриата, специалитета и магистратуры Национального исследовательского университета «Высшая школа экономики», утвержденное ученым советом НИУ ВШЭ 25.03.2022, протокол № 03;

 - Приказ генерального директора ООО "ГЭТ Э БЛАНКЕТ" о начале разработки программно-аппаратной системы автоматизации краткосрочной аренды от 09.01.2024.

# Назначение разработки 

Главная цель программно-аппаратного продукта: сделать возможной автоматизированную краткосрочную аренду пледов (шеринга) через вендинговые аппараты, установленные на улицах и в парках города. Для этого необходимо: 

- иметь возможность автономно сдать в аренду и вернуть плед,

- иметь возможность проводить обслуживание автоматов,

- иметь возможность собирать диагностические и иные данные с автоматов.

Для достижения поставленных целей требуется выполнить следующие задачи: 

- Реализовать программную систему для клиентов сервиса, которая обеспечивает автономную и автоматическую аренду пледов через вендинговые автоматы:

    - реализовать возможность взымания платы с клиентов,

    - реализовать возможность взятия пледа из автомата,

    - реализовать возможность возврата пледа в автомат,

    - реализовать возможность нахождения ближайшего к клиенту автомата.

- Реализовать программную систему для технического обслуживания автоматов: 

    - реализовать возможность открытия ячейки автомата,

    - реализовать возможность изъятия грязных пледов из автомата, 

    - реализовать возможность выкладывания чистых пледов в автомат.

- Реализовать программную систему для мониторинга собираемых данных: 

    - реализовать возможность просмотра графиков количества взятий пледов в аренду из автомата,

    - реализовать возможность просмотра графиков количества возвратов пледов из аренды в автомат.

# Требования к программной системе  

Данной системой будут пользоваться: 

- Клиенты коммерческого проекта -- люди, гуляющие вечерами, когда на улице начинает холодать, а форма одежды была выбрана на более теплое время суток.

- Специалисты технического обслуживания автоматов -- специалисты, задачами которых является поддержка рабочего состояния автоматов и выкладка/сбор пледов.

- Системные администраторы -- специалисты, занимающиеся поддержкой работы программно-аппаратного комплекса.

- Аналитики -- специалисты, занимающиеся анализом статистики взятий и возвратов пледов за определенный период.

Определенные сценарии использования системы представлены ниже.

Выделены следующие сценарии использования для не аутентифицированного клиента коммерческого проекта:  

- Отобразить информацию о местоположении автоматов на карте.

- Отобразить информацию об остатке пледов в автомате на карте.

Выделены следующие сценарии использования для аутентифицированного клиента коммерческого проекта:  

- Отобразить информацию о пледах, находящихся в аренде у клиента в данный момент: тариф, время использования, общая цена аренды. 

- Взять плед в аренду: выбрать автомат, выбрать ячейку, открыть ячейку, забрать плед, закрыть ячейку.

- Добавить банковскую карту в список карт для оплаты: выбрать операцию добавления новой карты, ввести данные карты (номер, cvv, дата истечение срока действия), подтвердить добавление карты пробным списанием.

- Определить банковскую карту как стандартную для оплаты: выбрать операцию определения карты по умолчанию, выбрать необходимую карту.

- Вернуть плед: выбрать автомат, выбрать ячейку, открыть ячейку, положить плед, закрыть ячейку.

Для обобщения сценариев использования построена UML диаграмма прецедентов, представленная в ПРИЛОЖЕНИЕ А.

Выделены следующие сценарии использования для специалиста технического обслуживания автоматов:

- Изъять использованные пледы из автомата: выбрать автомат, открыть ячейки, отметить наличие/отсутствие пледа в ячейке, забрать пледы, закрыть ячейки.

- Вложить чистые пледы в автомат: выбрать автомат, открыть ячейки, положить чистые пледы, закрыть ячейки.

- Открыть конкретную ячейку автомата: выбрать автомат, в рамках автомата выбрать ячейку по номеру, запустить операцию открытия ячейки.

- Закрыть конкретную ячейку автомата: выбрать автомат, в рамках автомата выбрать ячейку по номеру, выбрать ячейку, запустить операцию закрытия ячейки.

Для обобщения сценариев использования построена UML диаграмма прецедентов, представленная в ПРИЛОЖЕНИЕ Б.

Выделены следующие сценарии использования для аналитика и системного администратора:

- Отобразить статистику взятий в аренду из автоматов за определенный 
  
  период.

- Отобразить статистику возвратов пледов в автоматы за определенный 
  
  период.

- Экспорт статистики в файл формата CSV.

Для обобщения сценариев использования построена UML диаграмма прецедентов, представленная в ПРИЛОЖЕНИЕ В. 

## Требования к функциональным характеристикам

Требования обеспечивающие клиентов коммерческого проекта: 

- Система должна отображать номер ячейки автомата при взаимодействии клиента с ней.

- Система должна отображать карту с указанием местоположения автоматов и пользователя.

- Система должна отображать информацию о количестве доступных пледов в автоматах на карте.

- Система должна отображать информацию о пледах, находящихся в аренде пользователем на данный момент, а именно тариф, время пользования, общая цена аренды.

- Система должна отображать данные пользователя (номер телефона) на основной странице.

- Система должна позволять добавлять банковскую карту для оплаты с основной страницы.

- Система должна позволять указывать основную банковскую карту для оплаты.

- Пользователь должен иметь возможность выбрать автомат посредством ввода уникального кода автомата.

- Система должна предоставлять возможность выбора автомата посредством перехода по уникальной ссылке.

- Пользователь должен иметь возможность взять в аренду до 5 пледов. 

- Система должна предоставлять возможность закрытия ячейки по указанию пользователя.

- Система должна предоставлять фотографии автомата.

- Система должна отображать список возможных тарифов для аренды пледа.

- Система должна позволять выбрать один из возможных тарифов для аренды пледа.

- Система должна позволять выбрать основную банковскую карту до оплаты тарифа.

Требования обеспечивающие специалистов технического обслуживания автоматов:

- Система должна отображать номер ячейки автомата при взаимодействии специалиста с ней.

- Система должна позволять выбирать автомат один раз для выполнения нескольких операций.

- Система должна организовать изъятие использованных пледов из автомата.

- Система должна позволять отмечать отсутствие пледа в ячейке (данное действие требует подтверждения).

- Система должна организовать выкладывание чистых пледов в автомат. 

- Система должна позволять открывать определенную ячейку автомата.

- Система должна позволять закрывать определенную ячейку автомата.

Требования обеспечивающие аналитиков и системных администраторов:

- Система должна отображать графики по количеству взятий пледов в аренду из определенного автомата за определенный период.

- Система должна отображать графики по количеству возвратов пледов в определенный автомат за определенный период.

- Система должна иметь возможность экспортировать данные в формате CSV.

## Требования к надежности 

- Система должна обеспечивать бесперебойное функционирование в период с 8:00 до 24:00 по месту расположения автоматов, проведение технического обслуживания допускается только в нерабочее время при дополнительном согласовании с техническим директором. 

- В случае отказа системы, выполнение задач должно быть перехвачено резервной копией модуля для обеспечения бесперебойной работы.

- При сбоях система не должна терять данные о взятых пледах, проводимых денежных и иных операций.

- Информация об отказе должна быть предоставлена системным администраторам в течении минуты после возникновения внештатной ситуации.

- Задержка ответа системы на запросы пользователей не должна превышать 3 секунд. 

- Система должна гарантировать конфиденциальность персональных данных и соблюдение стандартов безопасности данных в соответствии с законодательством РФ в сфере банковских операций. 

- Система должна обеспечивать защиту от неавторизованного доступа (подразумевается, что если возможность доступа не указана, то она отсутствует): 

    - клиенты коммерческого проекта не имеют доступа к изменению данных в системе, за исключением изменения персональных данных, исключая данные о номере телефона, также имеют возможность полного удаления персональной информации; 

    - специалисты технического обслуживания автоматов имеют возможность изменения данных состояния автоматов и ячеек, исключая данные относимые к проведению банковских операций;

    - системные администраторы не должны иметь прямого доступа к данным, допускается только изменение схемы хранения данных в соответствие с схемой, предоставляемой разработчиком;

    - аналитики не имеют возможности изменения данных, доступ предоставляется к аналитическим данным без указания персональных данных пользователей.

- Разработанная система должна соответствовать нормам федерального закона № 152 “О персональных данных”. 

- Разработанная система должна соответствовать нормам федерального закона № 395-1 ”О банках и банковской деятельности”. 

- Разработанная система должна соответствовать нормам федерального закона № 115 “О противодействии легализации (отмыванию) доходов, полученных преступным путем, и финансированию терроризма”. 

## Условия эксплуатации

- Система должна обеспечивать возможность эксплуатации персоналом техничского обслуживания, не имеющим профильного технического образования. Для обучения персонала пользованием системой должно быть создано руководство пользования.

- Система не должна ограничивать количество персонала техничского обслуживания.

## Требования к составу и параметрам технических средств

- В случае невозможности предоставления вендиногового аппарата на этапе разработки, тестирование должно производится по средством эмуляции взаимодействия с ним.

- Технологии, используемые в разработке, должны быть свободно распространяемые и не должны быть подвержены влиянию санкций.

- Система должна быть реализована как веб-решение, не требующее установки на устройства конечных пользователей. 

## Требования к информационной и программной совместимости 

- Программная система должна иметь возможность развертывания на ЭВМ, виртуальной ЭВМ или множестве ЭВМ или виртуальных ЭВМ под управлением операционных систем с ядром Linux версии 5.4 и выше.

- Система должна обеспечивать внутреннее взаимодействие с использованием виртуальных локальных сетей защищенных алгоритмами шифрования.

- Программная система должна отображаться через браузеры выпуска не старее 2019 года.

## Требования к маркировке и упаковке 

Исходный код системы должен хранится с использованием системы версирования кода Git. 

## Требования к транспортированию и хранению 

- Исходный код должен быть передан в собственность ООО "ГЭТ Э БЛАНКЕТ", но не является коммерческой тайной. 

- Распространение кода между разработчиками должно происходить через системы удаленного версирования с возможностью автоматического непрерывного развертывания (GitHub, GitLab и подобных).

# Требования к программной документации  

Должна быть предоставлена следующая документация: 

- руководство развертывания, эксплуатации и поддержки системы;

- руководство пользователя техническим сервисом;

- руководство пользования аналитической системой;

- описание функций API сервисов в соответствии с нотацией OpenAPI.

# Технико-экономические показатели

Необходимость проекта обусловлена потребностью создания собственной программно-аппаратной системы для реализации коммерческого проекта по краткосрочной аренде через вендинговые аппараты. Не существует аналогичного программного обеспечения, обладающего подобным функционалом, так как реализуется инновационная бизнес-модель. 

Разработка программно-аппаратного продукта позволит реализовать коммерческий проект, по финансовой модели которого средний доход с 1 автомата составит 120 тысяч рублей в месяц, следовательно, 1 440 000 рублей в год, при рентабельности до 50% в сезон или 25% за год.

Бизнес-модель заключается в создании нескольких тарифов, при этом себестоимость одной покупки составляет 56 рублей. Средний чек -- двести рублей. При этом точкой безубыточности будет продажа 12 пледов в день на один автомат, а рассчитываемое среднее количество покупок 22. 

Оценка рынка: TAM составляет 20 млрд рублей в год, SAM -- 2 млрд рублей, SOM -- 1 млрд рублей. 

# Стадии и этапы разработки 

Ниже представлена иерархическая структура выполняемых работ.

1. Проектирование разрабатываемой системы 

    1. Определение архитектуры разрабатываемой системы 

    1. Определение программных решений, используемых в ходе разработки системы 

    1. Формирование концепции визуального облика системы

    1. Определение средств разработки и взаимодействия команды

1. Описание внутреннего распорядка разработки 

    1. Формальное описание задач проекта в информационной системе управления проектами

1. Разработка программного продукта 

    1. Разработка каждым участником проекта задач в соответствии с календарным планом и важностью задач

        1. Разработка сервиса аутентификации клиентов

        1. Разработка сервиса для специалистов технического обслуживания

        1. Разработка сервиса управления автоматами

        1. Разработка банковского сервиса оплаты

        1. Разработка пользовательского интерфейса

        1. Разработка мастер-сервиса -– связующее звено для всех вышеупомянутых сервисов 

    1. Формирование промежуточных выпусков программного продукта 

        1. Разработка алгоритмов автоматизированного развертывания 

        1. Подготовка и настройка серверов для развертывания продукта

        1. Настройка вспомогательного программного обеспечения

    1. Тестирование

        1. Разработка алгоритмов автоматического тестирования

        1. Проведение тестирования программного продукта

    1. Документирование

        1. Написание руководства развертывания системы

        1. Написание руководства пользователя техническим сервисом

        1. Написание руководства пользования аналитической системой

        1. Описание функций API сервисов в соответствии с нотацией OpenAPI

1. Проведение опытной эксплуатации 

    1. Проведение опытной эксплуатации системы в рамках лаборатории 

        1. Подготовка и установка модуля системы на вендинговый аппарат 

    1. Проведение опытной эксплуатации системы в рамках тестирования в парках с привлечением потенциальных клиентов 

        1. Проведение тестирования с привлечением консультанта 

        1. Проведение тестирования без привлечения консультанта

    1. Устранение обнаруженных проблем


# Порядок контроля и приемки 

Будут проведены следующие виды испытаний программной системы: 

- Тестирование на различных конфигурациях -- проверка работоспособности информационной системы при внедрении отдельных компонентов в условиях всех реализуемых заказчиком конфигураций аппаратных и программных ресурсов. 

- Приемочное тестирование -- проверка всех функциональных возможностей в рамках тестовой эксплуатации.  

Общие требования к приемке работы: 

- Проведение предварительных испытаний программной системы. 

- Фиксирование выявленных неполадок. 

- Устранение выявленных неполадок. 

- Проведение опытной эксплуатации. 
