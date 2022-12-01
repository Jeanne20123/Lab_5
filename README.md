# Интеграция экономической системы в проект Unity и обучение ML-Agent
Отчет по лабораторной работе #5 выполнил(а):
- Борщевская Жанна Александровна
- РИ-210911
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * |  |
| Задание 2 | * |  |

знак "*" - задание выполнено; знак "#" - задание не выполнено;
## Цель работы 
Интегрировать экономическую систему в проект Unity и обучить ML-Agent. 
## Задание 1
Открыла проект Unity, добавила в проект ml-agents-release_19. Поместила файл Economic.yaml в папку с проектом Unity. 
![image](https://user-images.githubusercontent.com/114568072/205131224-4cc351ea-6345-4962-8332-d6fc21f477a6.png)
Создала виртуальное пространство
![image](https://user-images.githubusercontent.com/114568072/205131919-003b492a-f029-4600-a9ff-992b400a9a5f.png)
Установила набор пакетов из третей лабораторной работы:
```py
a. (MLAgent) C:\WINDOWS\system32>pip install mlagents==0.28.0
b. (MLAgent) C:\WINDOWS\system32>pip install torch~=1.7.1 -f
https://download.pytorch.org/whl/torch_stable.html
```
Запустила обучение ML-Агента:
![image](https://user-images.githubusercontent.com/114568072/205132114-ee37f116-d2ab-435a-8b67-21868e2d3af0.png)
Мой процесс обучения модели:
![image](https://user-images.githubusercontent.com/114568072/205132259-172a24e2-99b3-407d-83a1-32a76aff358a.png)
Далее графики для оценки результатов обучения. Для этого
установила TensorBoard. 
```py
pip install tensorflow
```
![image](https://user-images.githubusercontent.com/114568072/205132571-9df59bae-2fc3-42c8-8297-952e5083d95b.png)
Запустила TensorBoard
![image](https://user-images.githubusercontent.com/114568072/205132712-5616fde8-6a2d-4aeb-85cb-355dd055963b.png)
time_horizon - Сколько шагов опыта нужно собрать для каждого агента, прежде чем добавлять его в буфер опыта.
![image](https://user-images.githubusercontent.com/114568072/205134481-8180d215-8428-4aef-b292-53ae1f495a73.png)
![image](https://user-images.githubusercontent.com/114568072/205134708-77fb5add-5ce6-408e-889f-f94b464299c9.png)
max_steps - Общее количество шагов, влияет на длительность обучения.
## Задание 2
Опишите результаты, выведенные в TensorBoard. 
![image](https://user-images.githubusercontent.com/114568072/205135485-09653b58-b3fe-41b3-9cbc-9c9900787edd.png)
