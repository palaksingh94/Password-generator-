# Password-generator-
The project is designed to be simple, user-friendly, and efficient. It takes input from the user, validates the entered values, and then generates a password accordingly. The logic of the program is structured in a clear and readable manner, making it easy to understand and modify. 
import random
import string

def generate_password(length, use_upper, use_lower, use_digits, use_symbols):
    characters = ""

    if use_upper:
        characters += string.ascii_uppercase
    if use_lower:
        characters += string.ascii_lowercase
    if use_digits:
        characters += string.digits
    if use_symbols:
        characters += string.punctuation

    if not characters:
        return "Error: No character types selected!"

    password = ''.join(random.choice(characters) for _ in range(length))
    return password


# ---- User Input ----
print("=== Password Generator ===")

length = int(input("Enter password length: "))

use_upper = input("Include uppercase letters? (y/n): ").lower() == 'y'
use_lower = input("Include lowercase letters? (y/n): ").lower() == 'y'
use_digits = input("Include numbers? (y/n): ").lower() == 'y'
use_symbols = input("Include special characters? (y/n): ").lower() == 'y'

# Generate password
password = generate_password(length, use_upper, use_lower, use_digits, use_symbols)

print("\nGenerated Password:", password)
