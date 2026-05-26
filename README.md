def calculator():
    print("--- Калькулятор на Python ---")
    
    while True:
        # Запрос первого числа с проверкой на корректность ввода
        try:
            num1 = float(input("Введите первое число: "))
        except ValueError:
            print("Ошибка: введено не число. Попробуйте еще раз.")
            continue

        # Запрос оператора
        operation = input("Выберите операцию (+, -, *, /) или 'q' для выхода: ").strip()

        # Выход из программы по требованию пользователя
        if operation.lower() == 'q':
            print("Работа завершена. До свидания!")
            break

        # Проверка корректности оператора
        if operation not in ['+', '-', '*', '/']:
            print("Ошибка: неверный знак операции.")
            continue

        # Запрос второго числа с проверкой на корректность ввода
        try:
            num2 = float(input("Введите второе число: "))
        except ValueError:
            print("Ошибка: введено не число. Попробуйте еще раз.")
            continue

        # Выполнение математических расчетов
        if operation == '+':
            result = num1 + num2
        elif operation == '-':
            result = num1 - num2
        elif operation == '*':
            result = num1 * num2
        elif operation == '/':
            # Защита от деления на ноль
            if num2 == 0:
                print("Ошибка: деление на ноль невозможно!")
                continue
            result = num1 / num2

        # Вывод итогового результата
        print(f"Результат: {num1} {operation} {num2} = {result}\n")
        print("-" * 30)

# Запуск калькулятора
if __name__ == "__main__":
    calculator()
