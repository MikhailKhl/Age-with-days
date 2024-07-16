from datetime import datetime, date

def calculate_age(birth_date):
    today = date.today()
    age = today.year - birth_date.year
    
    # Проверяем, был ли день рождения в этом году
    if (today.month, today.day) < (birth_date.month, birth_date.day):
        age -= 1
    
    # Вычисляем количество дней
    days = (today - birth_date.replace(year=today.year)).days
    
    return age, days

# Пример использования
birth_date = datetime(1990, 5, 15).date()
age, days = calculate_age(birth_date)
print(f"Возраст: {age} лет, {days} дней")
