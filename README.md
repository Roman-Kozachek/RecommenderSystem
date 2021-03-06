# Сравнение подходов к построению рекомендательных систем

Целью данной работы было сравнение двух подходов к построению рекомендаций: коллаборативного и гибридного (коллаборативного+контентного).  
В качестве датасета был использован MovieLens20M (https://www.kaggle.com/grouplens/movielens-20m-dataset).  
В качестве метрики - ROC AUC.  

Max ROC AUC на тестовой выборке для коллаборативного подхода: 0.936962   
Max ROC AUC на тестовой выборке для гибридного подхода: 0.877805  

Выводы:
1. Модели, использующие коллаборативный подход, способны демонстрировать достаточно высокие показатели метрики при правильной настройке гиперпараметров. Модель, на которой удалось достичь максимальных показателей метрики среди двух подходов, не пользовалась дополнительной информацией о пользователях или фильмах;
2. В работе с гибридными моделями стоит с осторожностью подходить к выбору свойств пользователей и объектов. Добавление большого числа дополнительных свойств может существенно сказываться на скорости обучения, а в отдельных случаях может также привести к падению значений метрики;
3. Выбор "правильных" дополнительных свойств способен увеличивать показатели метрики. Так, с добавлением информации о жанрах фильмов, показания ROC AUC остановились на значении в 0.64, но с добавлением информации о тэгах к фильмам, показания выросли до 0.87;

Итог:
Проведенный анализ показал, что коллаборативный подход демонстрирует, в среднем, лучший результат, чем коллаборативный подход с элементами контентного. Для использования моделей, основанных на коллаборативном подходе, требуется меньше подготовки и фильтрации данных, что является плюсом в случае необходимости построения простой и быстрой модели, не претендующей на рекордные значения точности. Однако, несмотря на то, что получить конкурентоспособные результаты для моделей, использующих гибридный подход, не получилось, говорить о превосходстве коллаборативного подхода над гибридным не приходится. Ввиду технических и временных ограничений, потенциал гибридного подхода не был раскрыт полностью. Вполне возможно, что более тщательный отбор свойств пользователей и объектов, вместе с подбором оптимальных гиперпараметров и продолжительным обучением может существенно увеличить показатели метрики моделей гибридного подхода. Потенциально, даже превзойти показатели моделей коллаборационного подхода.
