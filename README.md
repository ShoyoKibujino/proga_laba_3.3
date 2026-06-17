# proga_laba_3.3
# Задание task_03_03_03.
# Выполнил: Котова Е.А.
# Группа: ЦИБ-251

Исходный код:

    """
    Ошибки (номера строк через пробел, данная строка - №2): !!!
    """
    def first_vacant_row(seats):
    """Вернуть первый ряд, в котором имеется больше всего
    свободных мест и их количество.

    Возвращаемая нумерация рядов с 1. Если свободных мест нет, вернуть 0, 0.

    Параметры:
        - seats (list of list): информация о проданных билетах
                                (1 - продано, 0 - нет).

    Результат:
        - tuple (ряд, количество мест).
    """
      max_count = 0
      max_row = 0
      for row_index, row in enumerate(seats):
        available_seats_count = row.count(0)  # 0 - пусто
        if available_seats_count >= max_count:
            max_row = row_index
            max_count = available_seats_count

      return max_row, max_count
    
Пример реализации: <img width="638" height="673" alt="image" src="https://github.com/user-attachments/assets/6ff48274-9bbe-4f33-ab91-0673b5d9326d" />

Исправленный код:
Отсутствует условие, когда свободных мест нет, условие >= заменено на >, чтобы при равном количестве свободных мест оставался первый встреченный ряд, возврат max_row + 1 для нумерации с 1
    
    """
    Ошибки (номера строк через пробел, данная строка - №2): 16 19 20 21
    """
    def first_vacant_row(seats):
    """Вернуть первый ряд, в котором имеется больше всего свободных мест и их количество.
    Возвращаемая нумерация рядов с 1. Если свободных мест нет, вернуть 0, 0.
    Параметры:
    - seats (list of list): информация о проданных билетах (1 - продано, 0 - нет).
    Результат:
    - tuple (ряд, количество мест).
    """
      max_count = 0
      max_row = 0
      for row_index, row in enumerate(seats):
        available_seats_count = row.count(0)  # 0 - пусто
        if available_seats_count > max_count:  # исправлено >= на > для "первого" ряда
            max_row = row_index
            max_count = available_seats_count
        if max_count == 0:
          return 0, 0
      return max_row + 1, max_count  # нумерация с 1

  Пример реализации: <img width="724" height="723" alt="image" src="https://github.com/user-attachments/assets/f6c5c282-c2a1-4f78-bbb9-6c3015e04680" />

