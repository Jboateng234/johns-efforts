import re

def evaluatePassword(password):
    # Check the basic requirements
    if (len(password) >= 12 and
        re.search("[A-Z]", password) and
        re.search("[a-z]", password) and
        re.search("[0-9]", password) and
        re.search("[!+-?]", password)):

        # Check for consecutive characters
        no_consecutive_chars = all(password[i] != password[i+1] for i in range(len(password)-1))

        # Evaluate the strength based on length and consecutive characters
        if len(password) < 15:
            return 1  # OK password
        elif 15 <= len(password) <= 16:
            return 2 if no_consecutive_chars else 1  # Good password if no consecutive characters
        else:
            return 3 if no_consecutive_chars else 2  # Very strong if no consecutive characters
    else:
        return 0  # Invalid password

# Prompt the user to input a password
user_password = input("Enter a password to evaluate: ")

# Evaluate the entered password and print the result
password_strength = evaluatePassword(user_password)
strength_messages = {
    0: "Invalid password.",
    1: "OK password.",
    2: "Good password.",
    3: "Very strong password."
}
print(strength_messages[password_strength])
