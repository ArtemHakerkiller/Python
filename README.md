def roman_to_integer(s):

roman_values = {
        'I': 1,
        'V': 5,
        'X': 10,
        'L': 50,
        'C': 100,
        'D': 500,
        'M': 1000
    }
    
 total = 0
    i = 0
    
while i < len(s):
        # Check if this is a subtraction case
        if i + 1 < len(s) and roman_values[s[i]] < roman_values[s[i + 1]]:
            # Subtract current value from the next value
            total += roman_values[s[i + 1]] - roman_values[s[i]]
            i += 2
        else:
            # Just add the current value
            total += roman_values[s[i]]
            i += 1
    
  return total
