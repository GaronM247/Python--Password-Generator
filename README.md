## Introduction 
 Today we will embark on a journey to master the art of crafting a sophisticated password generator using Python's `secrets` and `random` modules. Within this guide, you'll unveil the mechanics behind generating passwords that adhere to specific criteria, encompassing factors such as length and mandatory inclusions of uppercase letters, lowercase letters, digits, and special characters. This endeavor showcases your prowess in Python programming while addressing the crucial aspect of modern security practices.


**Operating System & Utilities Needed:**
 - <b> Windows 10 <b/>
 - <b> Python 3.x installed<b/>
 - <b> Command Prompt <b/>

 

 **Import Required Modules:**
   Import the necessary modules at the beginning of your Python script.
   ```python
   import secrets
   import string
   import random
   ```
**Define Character Sets:**
   Create separate strings for different character sets: lowercase letters, uppercase letters, digits, and special characters.
   ```python
   lower = string.ascii_lowercase
   upper = string.ascii_uppercase
   digits = string.digits
   special = string.punctuation
   allChars = lower + upper + digits + special
   ```
**User Input:**
   Ask the user for the desired length of the password and the minimum requirements for each character type.
   ```python
   pwLen = int(input("How long should the password be? "))
   minUpper = int(input("Minimum Upper Case: "))
   minLower = int(input("Minimum Lower Case: "))
   minDigits = int(input("Minimum Numbers: "))
   minSpec = int(input("Minimum Special: "))
   ```
**Generate the Password:**
   Begin constructing the password based on the user's input. Loop through each character type and add random characters to the password until the minimum requirements are met.
   ```python
   password = ""

   for i in range(minUpper):
       password += "".join(random.choice(upper))

   for i in range(minLower):
       password += "".join(random.choice(lower))

   for i in range(minDigits):
       password += "".join(random.choice(digits))

   for i in range(minSpec):
       password += "".join(random.choice(special))
   ```
**Fill Remaining Characters:**
   Calculate the number of characters remaining to reach the desired password length. Fill the remaining characters with a random selection from all character sets.
   ```python
   remaining = pwLen - minLower - minUpper - minDigits - minSpec

   for i in range(remaining):
       password += "".join(random.choice(allChars))
   ```
**Shuffle and Display:**
   Convert the password string into a list of characters and shuffle them randomly to enhance security. Finally, join the shuffled characters to create the password and display it to the user.
   ```python
   password = list(password)
   random.shuffle(password)
   print("Generated Password:", "".join(password))
   ```

**Running the Script:**
    - Open Command Prompt.
    - Navigate to the directory where your Python script is saved.
    - Run the script using the command:
      ```
      python script_name.py
      ```

