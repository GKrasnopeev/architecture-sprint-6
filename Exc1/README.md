
![InsureTech_технологическая_архитектура_to-be](/Exc1/InureTech_технологическая архитектура_to-be.jpg)

# Обоснование/Описание:
## Масштабирование
Выбран подход в виде горизонтального масштабирования ввиду того что клиентская база широко распределена по стране и может увеличиваться.
## Балансировка нагрузки
Выбран подход в виде применения GLSB для перенаправления пользователей по географической принадлежности к ближайшему кластеру
## Фейловер стратегия
Выбран подход active-active, если один кластер выйдет из строя, вся нагрузка будет перенаправлена на резервный кластер
## БД
Выбран подход в виде использования Patroni. Каждый экземпляр Postgre в кластере синхронизирован с другими экземплярами посредством потоковй репликации.
В рамках одного кластера данные дополнительно будут дополнительно реплицироваться на SLAVE ноды
## Шардирование
Шардирование на текущий момент решено было не использовать