## Исследование надёжности заёмщиков

Заказчик — кредитный отдел банка. Нужно разобраться, влияет ли семейное положение и количество детей клиента на факт погашения кредита в срок. Входные данные от банка — статистика о платёжеспособности клиентов.

Результаты исследования будут учтены при построении модели **кредитного скоринга** — специальной системы, которая оценивает способность потенциального заёмщика вернуть кредит банку.


### Шаг 1. Откройте файл с данными и изучите общую информацию. 

### Вывод

***Тип данных указан не верно в столбцах 'education_id', 'family_status_id', 'debt'***
- Разный регистр в столбце education
- Отрицательные значения в столбце days_employed
- Леммы в значениях в столбце purpose***

### Шаг 2. Предобработка данных

### Обработка пропусков

### Вывод

***Были обнаружены пропущенные значения в столбцах 'total_income' и 'days_employed'***
- Возможно люди не указали свой доход и время работы хотя некоторые из их написали что сейчас работают.
- В столбце 'days_employed' были отрицательные значения. Возможно это ошибка появилась при выгрузке данных
- Пропуски я заполнены в первом столбце с помощью  медианы. Так-как значения сильно отлчались 
- Во втором с помощью среднего значения.

### Замена типа данных

### Вывод

***Метод astype я выбрал так-как он подходит лучше всего в данном случае. Есть еще 1 метод to_numeric(),
но он перевождит строки в float.***

### Обработка дубликатов

### Вывод

**В таблице было не много дубликатов, но были слова с разным регистром, и несколько выбросов.**
- Использовал метод drop_duplicates()
- Возможно дубликаты появились из-за програмной ошибки.

### Лемматизация

### Вывод

***Из всех категорий я выделил 4 основные (недвижимость, жилье, автомобиль, образование, свадьба)***

### Категоризация данных

Зависимость между уровнем дохода и возвратом кредита в срок
### Вывод
***Я выделил основные категории которые мне понадобились в последующих пунктах***

### Шаг 3. Ответьте на вопросы
Зависимость между наличием детей и возвратом кредита в срок
### Вывод
***Есть. Семьи без детей отдают кредиты лучше, в то время, как многодетные семьи возвращают долги хуже. Мне кажется это связано с тем что на ребенка уходит очень много времени и денег. Получается в семье появляется тот, кто тратит, но не зарабатывает. Так же родители не могут зарабатывать так же как без детей, потому что их нужно воспитывать.***
- Зависимость между семейным положением и возвратом кредита в срок
### Вывод
***Те кто Не женат и не замужем а так же в гражданском браке чаще всего молодые, и плохо понимают как вообще работают кредиты, так-как финансовой грамнотности нету, или она на минимальном уровне пожэтому кредиты они возвращабт реже всех. Получается категория женат / замужем и  в разводе в основном люди среднего возраста и они более ответсвенные. В категории вдовец / вдова чаще всего встречаются пожилые они почти всега отдают деньги.*** 
### Вывод
***Богатые возвращают кредит реже чем бедные и даже нищщие. Возможно потому что большие деньги в основном зарабатывают предпрениматели, и кредит на бизнес обычно довольно большой и отдать его почти невозможно если дело прогорело. У бедных чаще всего просто нет денег чтоб вернуть, а вот к нищщим относяться в основном пенсионеры. Они более ответсвенные. Средний класс зарабатывает достаточно чтоб вернуть деньги банку и чаще всего у них стабильная работа.***
- Как разные цели кредита влияют на его возврат в срок
### Вывод
***Кредит на автомобиль возвращают реже всего потому что этот актив быстро теряет в цене, и требует довольно больших вложений, а многие не думают об этом при покупке. С образованием мне кажется людям чаще всего сложно и работать и учиться. На свадьбу чаще всего дарят деньги и семья может вместе погасить кредит, это не много проще чем делать это оджному, а недвижемость это та вещь за которую если не будешь платить просто выгонят, поэтому люди пытаются найти деньги где угодно чтоб погасить ипотеку***

### Шаг 4. Общий вывод
В среднем клиенты не возврают деньги примерно с одинаковой вероятностью.
Уровень дохода влияет сильнее всего на это. Так-же важной чертой является цель кредита, семейное положение и колдичество детей.
Семьи без детей отдают кредиты лучше, в то время, как многодетные семьи возвращают долги хуже. Те кто Не женат и не замужем а так же в гражданском браке чаще всего не отдают кредиты, а вот вдовец / вдова чаще всего отдают деньги. Богатые возвращают кредит реже чем бедные и даже нищщие. Средний класс зарабатывает достаточно чтоб вернуть деньги банку и обычно у них стабильная работа поэтому в этой категории они самые надежные заемщики. И Самые рискованные категории кредита это автомобиль и образование, а вот самые защищенные это недвижемость.
Портрет самого надежного заёмщика - У него нет детей, вдовец, с заработком от 195759.75 до 2265604 и пытающийся взять кредит на недвижемость.
Портрет самого рискованного заёмщика - У него 4 ребенка, не женат или в гражданском браке, и с доходом от 2265604 и пытается он взять кредит на машину или образование. 