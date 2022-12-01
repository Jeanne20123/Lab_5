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
![image](https://user-images.githubusercontent.com/114568072/205137968-a44b2d88-99b0-4e8c-9cc2-84baf7c892d6.png)
```py
behaviors:
  Economic:
    trainer_type: ppo #выбирает тип обучения с поощерением
    hyperparameters: #перечисляем гиперпараметры объекта
      batch_size: 1024 #переменноя количество опыта на каждой итерации
      buffer_size: 10240 #общее количество опыта
      learning_rate: 3.0e-4 #начальная скорость обучения
      learning_rate_schedule: linear #
      beta: 1.0e-2 #
      epsilon: 0.2 #
      lambd: 0.95 #
      num_epoch: 3 #количество проходов, которые необходимо выполнить      
    network_settings: #сетевые настройки
      normalize: false #применяется ли нормализация к входным данным
      hidden_units: 128 #количество единиц в скрытых слоях нейронной сети
      num_layers: 2 #количество скрытых слоев нейронной сети
    reward_signals: #синналы вознаграждения
      extrinsic: #внешние св-ва сигналов
        gamma: 0.99 #
        strength: 1.0 #
    checkpoint_interval: 500000 #
    max_steps: 750000 # максимальное количество шагов
    time_horizon: 64 # временной горизонт
    summary_freq: 5000 #суммарная частота
    self_play: #
      save_steps: 20000 
      team_change: 100000 
      swap_steps: 10000 
      play_against_latest_model_ratio: 0.5 
      window: 10 
```
time_horizon - Сколько шагов опыта нужно собрать для каждого агента, прежде чем добавлять его в буфер опыта.
![image](https://user-images.githubusercontent.com/114568072/205134481-8180d215-8428-4aef-b292-53ae1f495a73.png)
![image](https://user-images.githubusercontent.com/114568072/205139165-5e4ec934-0b3d-4569-bd9a-d44301e468a9.png)

max_steps - Общее количество шагов, влияет на длительность обучения.
## Задание 2
Опишите результаты, выведенные в TensorBoard. 

