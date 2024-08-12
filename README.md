Кластеризация дорожных сетей и автобусных остановок 

Возможности:
 1. Кластеризация дорожных сетей произвольных российских городов
 2. Кластеризация автобусных остановок Санкт-Петербурга

Необходимо:
1. Установить БД neo4j
2. Плагин graph-data-science для neo4j
3. Создать бд и ввсети имя, пароль, порт в соответсвующие переменные в программе

Кластеризация дорожных сетей:
 1. create-db-graph.create_graph_db(name) - запустить(name - имя города), создастся отношения в бд neo4j
 2. louvain.louvain_clustering(graph_name) - запустить(graph_name - имя создоваемого графа), запустится кластеризация методом louvain,
   выведется модулярность кластеризации, в отношение запишется id группы в кластеризации
 3. leiden.leiden_cluster(graph_name) - запустить(graph_name - имя создоваемого графа), запустится кластеризация методом leiden,
   выведется модулярность кластеризации, в отношение запишется id группы в кластеризации
 4. Можно визуализировать результаты например использовав neo4j Bloom, расположить точки в географическом положении и раскрасив в соответсвии с группами кластеризации

Кластеризация сетей автобусных остановок Санкт-Петербугра:
 1. create_saint_petersubrg_bus_graph_db() - запустить, спарсится данные с сайта https://kudikina.ru данные о автобусных остановках, в виде: Вершины - остановки(географическое положение остановки,
  название остановки, список автобусных маршрутов в которых включена остановка); Связи - маршруты между соседними остановками внутри одного автобусного маршрута(название маршрута,
   длительность перемещения между соединяемыми остановками)
 2. louvain.louvain_clustering(graph_name) - запустить(graph_name - имя создоваемого графа), запустится кластеризация методом louvain,
   выведется модулярность кластеризации, в отношение запишется id группы в кластеризации
 3. leiden.leiden_cluster(graph_name) - запустить(graph_name - имя создоваемого графа), запустится кластеризация методом leiden,
   выведется модулярность кластеризации, в отношение запишется id группы в кластеризации
 4. Можно визуализировать результаты например использовав neo4j Bloom, расположить точки в географическом положении и раскрасив в соответсвии с группами кластеризации
