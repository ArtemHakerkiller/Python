def roman_to_int(roman):
    roman_numerals = {
        'I': 1, 'V': 5, 'X': 10, 'L': 50,
        'C': 100, 'D': 500, 'M': 1000
    }
    
    total = 0
    prev_value = 0

    for char in reversed(roman):
        current_value = roman_numerals[char]
        if current_value < prev_value:
            total -= current_value
        else:
            total += current_value
        prev_value = current_value

    return total
    
roman_number = input("Введіть римське число: ").upper()

    result = roman_to_int(roman_number)
    print(f"Звичайне число: {result}")
except KeyError:
    print("Некоректне римське число")

