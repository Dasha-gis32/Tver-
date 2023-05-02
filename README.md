# Tver-
#### Состав команды:
Глушенкова Дарья, Бурая Екатерина, Легецкая Маргарита, Болотная Полина
#### Ссылка на карту: https://dasha-gis32.github.io/Tver-/
#### Краткая информация о городе
Тверь занимает территорию более 147 кв.км. Город расположен в 167 километрах от Москвы и в 485 километрах от Санкт-Петербурга. С юга к Твери подступает моренная Калининская гряда. Климат умеренно-континентальный: средняя температура января -9,6 град С, июля +18,2 град С, среднее годовое количество осадков - 593 мм. Тверь находится на берегах рек Волга, Тверца, Тьмака, Лазурь, Соминка. Современная территория города включает ряд естественных лесопарков: Комсомольскую, Первомайскую, Бобачевскую, Березовую рощи и Сахаровский парк (в 1982 объявлены государственными заказниками).
#### Описание используемых данных с указанием источников
1. bounds.geojson - границы города Твери (источник: OpenStreetMap)
2. points.geojson - точки всех ОКН в границах Твери (источник: https://drive.google.com/file/d/1nx_61rfv_gUAUypuD2FmMFGztWZXdo0e/view) 
3. polygon_2.geojson - полигоны всех ОКН в границах твери (отрисованы вручную)
4. ansamble.geojson - точки ансамблей и достопримечательных мест в границах Твери (источник: https://drive.google.com/file/d/1nx_61rfv_gUAUypuD2FmMFGztWZXdo0e/view; были отфильтрованы данные, убраны памятники из базы) 
#### Описание основных методов
1. Метод to_crs для приведения всех слоёв к одной проекции
2. Присоединение атрибутивной таблицы одного слоя к другому через sjoin
3. Создание сетки
4. Создание веб-карты через folium.map
5. Создание картограммы на базе сетки через folium.Choropleth
6. Добавление различных слоёв на веб-карту через folium.GeoJson
7. Агрегирование точек с помощью плагина MarkerCluster в библиотеке folium
8. Добавление виджетов на карту с использованием различных плагинов (MousePosition, Fullscreen)
#### Что было самым сложным в работе
Самым сложным было разобраться со всем кодом впринципе :) Постоянно что-то не работало, хотя делали также как в примере. Начинало работать только с пятого раза при одинаковых действиях. Проблемы возникали почти на каждом небольшом шаге (агрегирование точек, добавление административных границ и тд), поэтому не уложились в изначальный дедлайн, но в конце концов с большей частью задач нам удалось справиться
#### Что получилось в работе и вы можете этим гордиться
1. Получилось самостоятельно написать функцию для добавления слоёв: административные границы города, достопримечательные места и ансамбли
2. Получилось самостоятельно присоединить атрибуты одного слоя (точек) к другому слою (полигоны). Изначально в слое с полигонами были только номера объектов
3. Получилось сделать все элементы задания - сделать сетку с картограммой, сделать агрегирование точек, добавить все слои и виджеты
4. Ещё мы сделали названия слоёв и легенды на русском языке, сделали административные границы сразу видимыми при открытии карты (то есть слой включён автоматически изначально) и изменили цвет сетки из примера
#### Что не получилось и почему
1. Не получилось отобразить названия полигонов зданий при наведении на них курсора. При написании кода точно также как в примере, возникает ошибка 'NoneType' object is not subscriptable. Специально для такого отображения мы присоединили атрибутивную таблицу точек ОКН к атрибутивной таблице полигонов, но всё равно не заработало, хотя механизм кажется понятным, писать через tooltip 
2. Не получилось поменять цвета административных границ и полигонов. Меняем цвет в коде в поле color, но цвет просто не меняется
