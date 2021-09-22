# Create a Random Password Generator Using Python

The standard password requirements I have typically seen are:
1. At least one upper case letter
2. At least one lower case letter
3. At least one symbol
4. At least one number
5. Password length requirements vary from app to app but there typically is a min and max number of characters needed.


## Installation

Follow the instructions on the [Python website](https://www.python.org/downloads/) to install the latest version of Python on your OS.

## Usage

```python
#Password Generator Project
import random

# List of the different character types for creating passwords
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
capital_letters = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']
all_keys = letters + capital_letters + numbers + symbols

print("Welcome to the PyPassword Generator! \nThis tool will generate a random password that includes upper case letters, lower case letters, numbers, and symbols")

# Different websites require different minimum character password length and might have different maximums. Prompt the user for this info.
min_input = int(input("What is the minimum number of characters your password should be? "))
max_input = int(input("What is the maximum number of characters your password should be? "))

# Randomly select a password length between the min and max number of characters.
password_length = (random.choice(range(min_input, max_input + 1)))

# Create a blank list to generate the password into.
password = []

# Add one of each character type.
# Some applications require passwords to include at least one upper case letter, lower case letter, symbol and number.
# Adding one of each will meet the minimum requirements.
password.append(random.choice(letters))
password.append(random.choice(capital_letters))
password.append(random.choice(numbers))
password.append(random.choice(symbols))

# Add in random characters from each type to populate the remainder of the password.
for i in range(1, password_length - 3):
    if len(password) < password_length:
        password.append(random.choice(all_keys))

# Shuffle the password list to randomize it.
random.shuffle(password)
# Concatenate the individual characters in the password list into a string with the join function.
final_random_password = ''.join(password)

print(f"Your password is: {final_random_password}")
```

