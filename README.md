
### Sentiment Analysis for Financial News using BERT


#### Задача

**Задача** - оценка тональности новостных заголовков на тему экономики. Данные для этого задания были взяты на www.kaggle.com в виде таблицы формата cvs, в которой хранятся тексты заголовков, а также их тональности. Новостным заголовкам в датасете могут присвоены 3 тональности, которые являются таргетами: положительная, негативная и нейтральная. Оценивают качество моделей в таких задачаях зачастую двумя способами:мера F1 и accuracy.
____

Sentiment Analysis для финансовых новостей - это не новая задача в NLP:существует множество статей на эту тему (например, https://arxiv.org/pdf/1908.10063.pdf). В данной статье сравниваются  метод tranfer learning с различными предобученными моделями (BERT, ELMO). BERT показал наилучшие результаты, поэтому ему было отдано предпочтение в самом проекте. Метод tranfer learning заключается в том, чтобы дообучить уже предобученную модель на каких-то специальных данных (в этом случае - финансовом домене), таким образом можно добиться state-of-the-art. С помощью ресурса http://nlpprogress.com/english/sentiment_analysis.html  выясняется, что BERT действительно очень часто используется в таких задачах как предобученная модель. 

____
#### Бейзлайн
1. Предобработка данных ( токенизация, приведение всех заголовков к одной выбранной длине (паддинг), маскирование для BERT, специальные токены и т.д.)
2. Создание датасета
3. Дообучение модели на последнем линейном слое
4. Получение предсказаний
5. Анализ предсказаний

____
Получилось достичь довольно неплохих результатов, близких к state-of-the-art.Самым сложным оказалось делать маскирование для BERTa.
