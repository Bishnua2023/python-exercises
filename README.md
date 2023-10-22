# python-exercises
pythone module exercises

'''1.Install the PyCharm IDE. Write a program that greets you by your own name.


user_name = input("Enter your name: ")
print(f"Hello, {user_name}!")

2. variables and interactive program
1.
user_name = input("Enter your name: ")
print(f"Hello, {user_name}!")

2.

import math

radius = float(input("Enter the radius of the circle: "))
area = math.pi * (radius ** 2)
print(f"The area of the circle with radius {radius} is {area:.2f}")

#3.Write a program that asks the user for the length and width of a rectangle. The program then prints out the perimeter and area of the rectangle. The perimeter of a rectangle is the sum of the lengths of each four sides.

length = float(input("Enter the length of the rectangle: "))
width = float(input("Enter the width of the rectangle: "))

# Calculate the area and perimeter of the rectangle
area = length * width
perimeter = 2 * (length + width)

# Print the results
print(f"The area of the rectangle is {area:.2f}")
print(f"The perimeter of the rectangle is {perimeter:.2f}")

#4.Write a program that asks the user for three integer numbers. The program prints out the sum, product, and average of the numbers.

num1 = int(input("Enter the first integer number: "))
num2 = int(input("Enter the second integer number: "))
num3 = int(input("Enter the third integer number: "))

total = num1 + num2 + num3
product = num1 * num2 * num3
average = total / 3  # Calculate the average by dividing the total by the number of values


print(f"The sum of the numbers is: {total}")
print(f"The product of the numbers is: {product}")
print(f"The average of the numbers is: {average:.2f}")

#5.Write a program that asks the user to enter a mass in medieval units: talents (leiviskä), pounds (naula), and lots (luoti). The program converts the input to full kilograms and grams and outputs the result to the user:

talents = float(input("Enter talents: "))
pounds = float(input("Enter pounds: "))
lots = float(input("Enter lots: "))

# conversion factors
pounds_per_talent = 20
lots_per_pound = 32
grams_per_lot = 13.3

# (kilograms and grams)
total_grams = (talents * pounds_per_talent + pounds) * lots_per_pound * grams_per_lot
kilograms = int(total_grams // 1000)
grams = total_grams % 1000

print(f"The weight in modern units:")
print(f"{kilograms} kilograms and {grams:.2f} grams.")
#6.Write a program that draws two random combinations of numbers for a combination lock:
#a 3-digit code where each number is between 0 and 9.
#a 4-digit code where each number is between 1 and 6.

import random

# 3-digit combination lock code
def generate_3_digit_code():
    return [random.randint(0, 9) for _ in range(3)]

# 4-digit combination lock code with numbers between 1 and 6
def generate_4_digit_code():
    return [random.randint(1, 6) for _ in range(4)]

# two random combinations
combination1 = generate_3_digit_code()
combination2 = generate_4_digit_code()

# Print the combinations
print("3-Digit Combination: ", end="")
for digit in combination1:
    print(digit, end="")
print()

print("4-Digit Combination: ", end="")
for digit in combination2:
    print(digit, end="")
print()

#3 Conditional structures (if)
#1. Write a program that asks a fisher the length of a zander in centimeters. If the zander does not fulfill the size limit, the program instructs to release the fish back into the lake and notifies the user of how many centimeters below the size limit the caught fish was. A zander must be 42 centimeters or longer to meet the size limit.

zander_length = float(input("Enter the length of the zander in centimeters: "))

size_limit = 42

if zander_length >= size_limit:
    print("Congratulations! The zander is of legal size.")
else:
    centimeters_below_limit = size_limit - zander_length
    print(f"The zander is {centimeters_below_limit:.2f} centimeters below the legal size limit.")
    print("Please release the fish back into the lake.")

#2.Write a program that asks the user to enter the cabin class of a cruise ship and then prints out a written description according to the list below. You must use an if/elif/else structure in your solution.

cabin_class = input("Enter the cabin class (LUX, A, B, C): ")

if cabin_class == "LUX":
    print("Upper-deck cabin with a balcony.")
elif cabin_class == "A":
    print("Above the car deck, equipped with a window.")
elif cabin_class == "B":
    print("Windowless cabin above the car deck.")
elif cabin_class == "C":
    print("Windowless cabin below the car deck.")
else:
    print("Invalid cabin class.")

#3. Write a program that asks for the biological gender and hemoglobin value (g/l). The program the notifies the user if the hemoglobin value is low, normal or high.

# Get the gender input from the user using short forms (M or F)
gender = input("Enter your biological gender (M or F): ")
hemoglobin_value = float(input("Enter your hemoglobin value (g/l): "))
hemoglobin_ranges = {
    "M": (134, 167),
    "F": (117, 155),
}

if gender in hemoglobin_ranges:
    lower_range, upper_range = hemoglobin_ranges[gender]
    if lower_range <= hemoglobin_value <= upper_range:
        print("Your hemoglobin value is normal.")
    elif hemoglobin_value < lower_range:
        print("Your hemoglobin value is low.")
    else:
        print("Your hemoglobin value is high.")
else:
    print("Invalid gender. Please enter 'M' for male or 'F' for female.")

#4.Write a program that asks the user to enter a year and notifies the user whether the input year is a leap year. A year is a leap year if it is divisible by four. However, years divisible by 100 are leap years only if they are also divisible by 400.

year = int(input("Enter a year: "))
if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
    print(f"{year} is a leap year.")
else:
    print(f"{year} is not a leap year.")
#4. While loops (while)
#1
num = 1
while num <= 1000:
    if num % 3 == 0:
        print(num)
    num += 1

#2
while True:
    inches = float(input("Enter inches (negative value to quit): "))
    if inches < 0:
        break
    centimeters = inches * 2.54
    print(f"{inches} inches is equal to {centimeters} centimeters.")

#3
numbers = []
while True:
    user_input = input("Enter a number (or press Enter to quit): ")
    if user_input == "":
        break
    numbers.append(float(user_input))

if numbers:
    print(f"Smallest number: {min(numbers)}")
    print(f"Largest number: {max(numbers)}")
else:
    print("No numbers entered.")

#4
import random

random_number = random.randint(1, 10)
attempts = 0

while True:
    guess = int(input("Guess the number (1-10): "))
    attempts += 1
    if guess < random_number:
        print("Too low!")
    elif guess > random_number:
        print("Too high!")
    else:
        print(f"Correct! You guessed the number in {attempts} attempts.")
        break

#5
username = "python"
password = "rules"
attempts = 0

while attempts < 5:
    input_username = input("Enter your username: ")
    input_password = input("Enter your password: ")
    if input_username == username and input_password == password:
        print("Welcome!")
        break
    else:
        print("Invalid login credentials. Try again.")
    attempts += 1

if attempts == 5:
    print("Access denied after 5 failed attempts.")

#6 Approximate Pi Value
import random

total_points = int(input("Enter the number of random points to generate: "))
points_inside_circle = 0
attempts = 0

while attempts < total_points:
    x = random.uniform(-1, 1)
    y = random.uniform(-1, 1)
    if x**2 + y**2 < 1:
        points_inside_circle += 1
    attempts += 1

pi_approximation = 4 * points_inside_circle / total_points
print(f"Approximation of Pi: {pi_approximation}")


#5. List structures and iterative loops (for)

#1 Roll Dice and Find Sum

num_dice = int(input("Enter the number of dice to roll: "))
total = 0

for _ in range(num_dice):
    roll = random.randint(1, 6)
    print(f"Rolled: {roll}")
    total += roll

print(f"Sum of the dice: {total}")

#2 Find Five Greatest Numbers in Descending Orde
numbers = []

while True:
    user_input = input("Enter a number (or press Enter to quit): ")
    if user_input == "":
        break
    numbers.append(float(user_input))

if numbers:
    numbers.sort(reverse=True)
    print("Five greatest numbers (descending order):")
    for i in range(min(5, len(numbers))):
        print(numbers[i])
else:
    print("No numbers entered.")

#3
def is_prime(num):
    if num <= 1:
        return False
    for i in range(2, num):
        if num % i == 0:
            return False
    return True

number = int(input("Enter an integer: "))
if is_prime(number):
    print(f"{number} is a prime number.")
else:
    print(f"{number} is not a prime number.")

#4
cities = []

for _ in range(5):
    city = input("Enter a city name: ")
    cities.append(city)

print("Cities entered:")
for city in cities:
    print(city)


#6. Functions

#1.
import random

def roll_dice():
    return random.randint(1, 6)

while True:
    result = roll_dice()
    print(f"Dice Roll Result: {result}")
    if result == 6:
        break
#2
import random

def roll_dice(sides):
    return random.randint(1, sides)

max_value = int(input("Enter the maximum number on the dice: "))
while True:
    result = roll_dice(max_value)
    print(f"Dice Roll Result: {result}")
    if result == max_value:
        break
#3
def gallons_to_liters(gallons):
    liters = gallons * 3.78541
    return liters

while True:
    gallons = float(input("Enter a volume in gallons (negative value to quit): "))
    if gallons < 0:
        break
    liters = gallons_to_liters(gallons)
    print(f"{gallons} gallons is equal to {liters} liters.")

#4
def sum_of_list(numbers):
    return sum(numbers)

num_list = [1, 2, 3, 4, 5]  # Replace with your list of integers
result = sum_of_list(num_list)
print(f"Sum of the numbers in the list: {result}")

#5
def remove_odd_numbers(numbers):
    return [num for num in numbers if num % 2 == 0]

num_list = [1, 2, 3, 4, 5]  # Replace with your list of integers
result = remove_odd_numbers(num_list)
print("Original list:", num_list)
print("List with odd numbers removed:", result)

#6
def calculate_unit_price(diameter, price):
    radius = diameter / 2
    area = 3.14159265359 * (radius**2)
    unit_price = price / area
    return unit_price

diameter1 = float(input("Enter the diameter of pizza 1 (in cm): "))
price1 = float(input("Enter the price of pizza 1 (in euros): "))
unit_price1 = calculate_unit_price(diameter1, price1)

diameter2 = float(input("Enter the diameter of pizza 2 (in cm): "))
price2 = float(input("Enter the price of pizza 2 (in euros): "))
unit_price2 = calculate_unit_price(diameter2, price2)

if unit_price1 < unit_price2:
    print("Pizza 1 provides better value for money.")
elif unit_price2 < unit_price1:
    print("Pizza 2 provides better value for money.")
else:
    print("Both pizzas provide the same value for money.")

#7. Tuple, set, and dictionary
#1
seasons = ("Winter", "Spring", "Summer", "Autumn")
month = int(input("Enter a month number (1-12): "))
season = seasons[(month - 1) // 3]
print(f"The corresponding season is {season}.")

#2
names_set = set()

while True:
    name = input("Enter a name (or press Enter to quit): ")
    if name == "":
        break
    if name in names_set:
        print("Existing name")
    else:
        print("New name")
        names_set.add(name)

print("Input names:")
for name in names_set:
    print(name)

#3

airport_database = {}

while True:
    print("Airport Database Menu:")
    print("1. Enter a new airport")
    print("2. Fetch information of an existing airport")
    print("3. Quit")

    choice = input("Select an option (1/2/3): ")

    if choice == "1":
        icao_code = input("Enter the ICAO code of the airport: ")
        airport_name = input("Enter the name of the airport: ")
        airport_database[icao_code] = airport_name
        print(f"Airport data for {icao_code} has been stored.")

    elif choice == "2":
        icao_code = input("Enter the ICAO code of the airport to fetch information: ")
        if icao_code in airport_database:
            airport_name = airport_database[icao_code]
            print(f"The name of the airport with ICAO code {icao_code} is: {airport_name}")
        else:
            print(f"No information found for airport with ICAO code {icao_code}.")

    elif choice == "3":
        print("Goodbye!")
        break

    else:
        print("Invalid choice. Please select a valid option (1/2/3).")
'''
