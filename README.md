# Разработка решения, позволяющего персонализировать предложения постоянным клиентам компании "В один клик" для увеличения их покупательской активности.

## Описание проекта
Интернет-магазин «В один клик» продаёт разные товары: для детей, для дома, мелкую бытовую технику, косметику и даже продукты. Отчёт магазина за прошлый период показал, что активность покупателей начала снижаться. Привлекать новых клиентов уже не так эффективно: о магазине и так знает большая часть целевой аудитории. Возможный выход — удерживать активность постоянных клиентов. Сделать это можно с помощью персонализированных предложений.
«В один клик» — современная компания, поэтому её руководство не хочет принимать решения просто так — только на основе анализа данных и бизнес-моделирования. У компании есть небольшой отдел цифровых технологий, и вам предстоит побыть в роли стажёра в этом отделе. 
Итак, вашему отделу поручили разработать решение, которое позволит персонализировать предложения постоянным клиентам, чтобы увеличить их покупательскую активность.

## Описание данных

***Предоставлены данные в нескольких таблицах:***

`market_file.csv`  
***Таблица, которая содержит данные о поведении покупателя на сайте, о коммуникациях с покупателем и его продуктовом поведении.***    
-   `id` — номер покупателя в корпоративной базе данных.
-   `Покупательская активность` — рассчитанный класс покупательской активности (целевой признак): «снизилась» или «прежний уровень».
-   `Тип сервиса` — уровень сервиса, например «премиум» и «стандарт».
-   `Разрешить сообщать` — информация о том, можно ли присылать покупателю дополнительные предложения о товаре. Согласие на это даёт покупатель.
-   `Маркет_актив_6_мес` — среднемесячное значение маркетинговых коммуникаций компании, которое приходилось на покупателя за последние 6 месяцев. Это значение показывает, какое число рассылок, звонков, показов рекламы и прочего приходилось на клиента.
-   `Маркет_актив_тек_мес` — количество маркетинговых коммуникаций в текущем месяце.
-   `Длительность` — значение, которое показывает, сколько дней прошло с момента регистрации покупателя на сайте.
-   `Акционные_покупки` — среднемесячная доля покупок по акции от общего числа покупок за последние 6 месяцев.
-   `Популярная_категория` — самая популярная категория товаров у покупателя за последние 6 месяцев.
-   `Средний_просмотр_категорий_за_визит` — показывает, сколько в среднем категорий покупатель просмотрел за визит в течение последнего месяца.
-   `Неоплаченные_продукты_штук_квартал` — общее число неоплаченных товаров в корзине за последние 3 месяца.
-   `Ошибка_сервиса` — число сбоев, которые коснулись покупателя во время посещения сайта.
-   `Страниц_за_визит` — среднее количество страниц, которые просмотрел покупатель за один визит на сайт за последние 3 месяца.

`market_money.csv`  
***Таблица с данными о выручке, которую получает магазин с покупателя, то есть сколько покупатель всего потратил за период взаимодействия с сайтом.***  
-   `id` — номер покупателя в корпоративной базе данных.
-   `Период` — название периода, во время которого зафиксирована выручка. Например,'текущий_месяц' или 'предыдущий_месяц'.
-   `Выручка` — сумма выручки за период.

`market_time.csv`  
***Таблица с данными о времени (в минутах), которое покупатель провёл на сайте в течение периода.***  
-   `id` — номер покупателя в корпоративной базе данных.
-   `Период` — название периода, во время которого зафиксировано общее время.
-   `минут` — значение времени, проведённого на сайте, в минутах.

`money.csv`  
***Таблица с данными о среднемесячной прибыли покупателя за последние 3 месяца: какую прибыль получает магазин от продаж каждому покупателю.***  
-   `id` — номер покупателя в корпоративной базе данных.
-   `Прибыль` — значение прибыли.

## План работы

- Загрузим и проанализируем предоставленные данные    
- Проведём исследовательский анализ данных  
- Проведем объединение таблиц  
- Проведем корреляционный анализ 
- Применим изученные модели с использованием пайплайнов  
- Проведем анализ важности признаков
- Выполним сегментацию покупателей
- Сделаем итоговые выводы  

## Общий вывод

***Описание задачи***

- Поставлена задача в необходимости разработать решение, которое позволит персонализировать предложения постоянным клиентам, чтобы увеличить их покупательскую активность.
- Необходимо было построить модель для предсказания вероятности снижения покупательской активности клиента в следующие три месяца
- Выделить сегмент покупателей и проанализировав разработать персонализированные предложения

***Описание исходных данных и проведенной предобработки***

- загружены и обработаны данные
- приведены в соответсвие типы данных 
- проведен анализ на поиск дубликатов и пропусков

***Проведенные этапы для поиска лучшей модели***

- проведено исследование корреляции между признаками 
- в процессе поиска к данным применено 4 типа моделей классифкации и на основе метрики roc-auc проведен отбор лучшей модели.
- на основе метрики roc-auc была отобрана лучшая модель SVC c использованием пайплайна
- построен график важности признаков полученной модели

***Выводы:***

***Признаки связанные с использованием интернета для ознакомления с продукцией и расширения объема продаж является ключевым по важности. Сотрудники компании "В один клик" должны уделять ему пристальное внимание.***

***Заметно влияние на покупательскую способность клиентов из категории «Товары для детей» маргетинговых коммуникаций компании и акционные продажи товаров.***

***Предложение активнее в дальнейшем использовать влияние этих признаков (маргетинговых коммуникаций компании и акционных продаж товаров) для расширения продаж и привлечения новых клиентов.***
