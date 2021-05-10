# Лабораторная работа 4.

**Цель лабораторной работы:**  Исследовать влияние различных техник аугментации
данных на процесс обучения нейронной сети на примере решения задачи классификации
Food-101 с использованием техники обучения Transfer Learning

**Задачи:**

1. С использованием [1], техники обучения Transfer Learning [2] и оптимальной
политики изменения темпа обучения, определенной в ходе выполнения
лабораторной #3, обучить нейронную сеть EfficientNet-B0 (предварительно
обученную на базе изображений imagenet) для решения задачи классификации
изображений Food-101 с использованием следующих техник аугментации данных [3]:
    a. Случайное горизонтальное и вертикальное отображение [4]
    b. Использование случайной части изображения [5]
    c. Поворот на случайный угол [6]
2. Для каждой индивидуальной техники аугментации определить оптимальный набор
параметров
3. Обучить нейронную сеть с использованием оптимальных техник аугментации
данных 2a-с совместно
<hr/>


## 1. С использованием, техники обучения Transfer Learning и оптимальной политики изменения темпа обучения, определенной в ходе выполнения лабораторной #3, обучить нейронную сеть EfficientNet-B0 (предварительно обученную на базе изображений imagenet) для решения задачи классификации изображений Food-101 с использованием следующих техник аугментации данных: Случайное горизонтальное и вертикальное отображение, Использование случайной части изображения, Поворот на случайный угол. ##


**Графики обучения EfficientNetB0 с использованием аугментации данных RandomFlip:**

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/117620529-38fa0280-b179-11eb-99e7-a455d3b72c8b.png)

***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/117620614-50d18680-b179-11eb-8fdb-114f32935762.png)


***Визуализация случайных изображений***


***Анализ полученных результатов***
Анализируя полученные данные, можно утверждать что оптимальным параметром для техник аугментации данных: a. Случайное горизонтальное и вертикальное отображение, является параметр Horizontal, так как с этим параметром достигается наибольная точность равная 67,97% и наименшее значение функции потерь, равное 1.209
<hr/>



**Графики обучения EfficientNetB0 с использованием аугментации данных RandomСrop:**

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/117627583-fb997300-b180-11eb-91c3-179d210bca6b.png)
***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/117621491-57143280-b17a-11eb-84a7-b860092158a4.png)


***Визуализация случайных изображений***


***Анализ полученных результатов***
Анализируя полученные данные, можно утверждать что оптимальным параметром для техник аугментации данных: b. Использование случайной части изображения, является параметр 300*250, так как с этим параметром достигается наибольная точность равная 66,83% и наименшее значение функции потерь, равное 1.246
<hr/>



**Графики обучения EfficientNetB0 с использованием аугментации данных RandomRotation:**

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/117623817-ede1ee80-b17c-11eb-9fee-6a9561b6ba56.png)
***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/117623897-fe926480-b17c-11eb-988a-765ccb741958.png)

***Визуализация случайных изображений***


***Анализ полученных результатов***
Анализируя полученные данные, можно утверждать что оптимальным параметром для техник аугментации данных: c. Поворот на случайный угол, являются параметры factor=0.04, fill_mode='reflect', так как с этими параметрами достигается наибольная точность равная 67,66% и наименшее значение функции потерь, равное 1.219
<hr/>


## 2. бучить нейронную сеть с использованием оптимальных техник аугментации данных 1a-с совместно. ##

**Графики обучения EfficientNetB0 с использованием оптимальных техник аугментации данных совместно**

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/117626321-a5780000-b17f-11eb-9ac9-3fd1b350021a.png)
***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/117626378-b6287600-b17f-11eb-8226-528ea8d4c142.png)

***Визуализация случайных изображений***


***Анализ полученных результатов***
Анализируя полученные данные, можно заметить, что значения полученые при совместной аугментации данных ниже, чем у начальной нейронной сети(нейронная сеть с  фиксированный темпом обучения), наблюдается разница точности в 0.5%.


***Вывод:***
В ходе выполнения лабораторной работы, я определил оптимальные значения для каждой из техник аугментации данных. Для RandomFlip это параметр mode=HORIZONTAL, для RandomCrop это параметр HEIGHT = 300, WIDTH = 250. Для RandomRotation - factor=0.04, fill_mode='reflect'. Но анализируя полученные данные можно утверждать, что совместное использование техник аугментации данных, не дает более высоких результатов, что видно из последних графиков точности, где показана точность исходной нейронной сети и нейронной сети с использованием оптимальных техник аугментации данных 2a-с совместно. Точность исходной сети составила 67.9% и значение функции потерь 1.209, а сети с использованием оптимальных техник аугментации данных составила 67,3% и функции потреь 1.236, наблюдается разница в точности в 0.5%.
