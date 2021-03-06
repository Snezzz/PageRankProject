# PageRankProject  
## Анализ популярности научных статей   
  Источник данных: ResearchGate  
Алгоритм:PageRank    
## Описание работы  
#### **Task:**
Собрать (найти) датасет с научными статьями и найти наиболее значимые статьи в каждой области, используя PageRank  
#### **Сбор данных**  
Много времени ушло на поиск подходящего датасета. В результате не было найдено хорошей версии и было решено собирать данные вручную. Остановилась на данных с сайта [ResearchGate](https://www.researchgate.net/).  
Реализован парсер -> тестирование парсера -> обнаружение проблем в парсинге    
### Список рассматриваемых научных областей  
1.Mathematics  
2.Biology  
3.Computer Science  
4.Physics  
5.Chemistry    
#### **Проблема**  
Проблема парсинга связана с тем, что при большом количестве обращений к сайту ему кажется, что это робот пытается получить данные, в связи с чем он запроашивает пройти верификацию. Возможно, существуют способы обхода данной проблемы, но я с ними не знакома.  
В связи с возникшей проблемой было принято решение собирать данные вручную.  
Логика сбора данных следующая:    
    1. Ищем популярную статью (на нее ссылается большое количество других статей)  
    2. Собираем данные о данной статье
    3. Собираем список ссылающихся статей и добавляем его в очередь
    4. Повторяем шаги с пункта 2 до тех пор, пока список не пуст  
Сбор данных основан на алгоритме BFS (поиск в ширину). В результате по такому подходу получилось собрать не большое количество данных, но зато получены интересные взаимосвязи между документами: есть те документы, что ссылаются на одну и ту же статью.  
Собранные данные хранятся в папке dataset в формате .csv.   
### Теория вкратце  
Мы исследуем документы и их цитируемость. Для анализа данных в данной работе используется теория графов, с которой связано рассматриваемое понятие **PageRank**.    
PageRank - алгоритм, с помощью которого мы можем определить "важные" документы - такие документы, на которые ссылаются чаще всего другие "выжные" документы. 
  
### Результаты  
![math_graph](visualization/math_graph.png)  
![biology_graph](visualization/bio_graph.png)  
![CS_graph](visualization/CS_graph.png)  
![physics_graph](visualization/physics_graph.png)  
![chemistry_graph](visualization/chemistry_graph.png)  
