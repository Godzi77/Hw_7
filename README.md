def safe_calculator(func):
    def wrapper(expression):
        try:
            result = func(expression)
            print(f"Результат: {result}")
            return result
        except Exception as e:
            print(f"Помилка: {e}")
    return wrapper


@safe_calculator
def calculate(expression):
    return eval(expression)

calculate("2 + 3 * 4")
calculate("10 / 0")  # помилка
calculate("2 +")     # помилка
