# Задание #
## Урок 6. Хранение и обработка данных ч3: множество коллекций Set. ##

 #### Скрыть Подумать над структурой класса Ноутбук для магазина техники - выделить поля и методы. Реализовать в java. ####

-Создать множество ноутбуков. -Написать метод, который будет запрашивать у пользователя критерий (или критерии) фильтрации и выведет ноутбуки, отвечающие фильтру. Критерии фильтрации можно хранить в Map. Например: Введите цифру, соответствующую необходимому критерию: 1 - ОЗУ 2 - Объем ЖД 3 - Операционная система 4 - Цвет … -Далее нужно запросить минимальные значения для указанных критериев - сохранить параметры фильтрации можно также в Map. -Отфильтровать ноутбуки их первоначального множества и вывести проходящие по условиям.

# Магазин ноутбуков - техническая документация #
Этот проект реализует систему управления магазином ноутбуков на Java. Ниже приведено подробное описание структуры и функционирования кода.

# Структура классов #
### Класс Laptop ###
Представляет отдельный ноутбук.

Поля:

* model: String - модель ноутбука
* ram: int - объем оперативной памяти (в ГБ)
* hddCapacity: int - объем жесткого диска (в ГБ)
* os: String - операционная система
* color: String - цвет ноутбука
* price: double - цена ноутбука

Методы:

* Конструктор, инициализирующий все поля
* Геттеры для всех полей
* Переопределенный метод toString() для строкового представления объекта

Класс LaptopStore

Управляет коллекцией ноутбуков и операциями над ними.

Поля:

* laptops: Set - множество ноутбуков
* random: Random - генератор случайных чисел

Методы:

* generateLaptops(int count): Генерирует заданное количество случайных ноутбуков
* displayAllLaptops(): Выводит информацию о всех ноутбуках
* filterLaptops(): Реализует интерактивную фильтрацию ноутбуков

Класс Main

Содержит точку входа в программу и управляет пользовательским интерфейсом.

### Функционирование кода ###

##### Генерация ноутбуков (метод generateLaptops) #####
1. Определяет массивы возможных значений для каждой характеристики ноутбука.
2. В цикле создает заданное количество ноутбуков, случайным образом выбирая значения из определенных массивов.
3. Генерирует случайную цену в диапазоне от 500 до 3000.
4. Добавляет созданный ноутбук в множество laptops.
##### Фильтрация ноутбуков (метод filterLaptops)

1. Предлагает пользователю ввести критерии фильтрации через консольное меню.
2. Сохраняет введенные критерии в Map<String, Object>.
3. Создает новое множество filteredLaptops, изначально содержащее все ноутбуки.
4. Проходит по всем ноутбукам, удаляя из filteredLaptops те, которые не соответствуют заданным критериям.
5. Выводит отфильтрованный список ноутбуков.

##### Главный цикл программы (метод main)

1. Создает экземпляр LaptopStore и генерирует 100 случайных ноутбуков.
2. Входит в цикл do-while, отображающий меню и обрабатывающий выбор пользователя.
3. В зависимости от выбора пользователя вызывает соответствующие методы LaptopStore.
4. Продолжает работу до тех пор, пока пользователь не выберет опцию выхода.

##### Особенности реализации

* Использование Set для хранения ноутбуков предотвращает дубликаты.
* Фильтрация реализована с использованием Map для хранения критериев, что позволяет легко добавлять новые критерии.
* Генерация случайных ноутбуков обеспечивает разнообразие данных для тестирования функциональности фильтрации.
##### Возможные улучшения

* Добавление возможности сохранения и загрузки данных из файла.
* Реализация более сложных алгоритмов фильтрации и сортировки.
* Создание графического пользовательского интерфейса.