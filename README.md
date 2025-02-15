# PackageSorting

def sort(width, height, length, mass):
    # Calculate volume
    volume = width * height * length
    
    # Check if the package is bulky
    is_bulky = volume >= 1000000 or width >= 150 or height >= 150 or length >= 150
    
    # Check if the package is heavy
    is_heavy = mass >= 20
    
    # Determine the correct stack
    if is_bulky and is_heavy:
        return "REJECTED"
    elif is_bulky or is_heavy:
        return "SPECIAL"
    else:
        return "STANDARD"
print(sort(100, 100, 100, 25))  # Output: SPECIAL (bulky and heavy)
print(sort(50, 50, 50, 15))     # Output: STANDARD (not bulky, not heavy)
print(sort(200, 200, 200, 10))  # Output: REJECTED (bulky and heavy)
print(sort(100, 100, 100, 19))  # Output: SPECIAL (bulky)
