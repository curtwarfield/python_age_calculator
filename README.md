# Python Age calculator

**Python** is a popular high-level programming language that is known for its simplicity, readability, and versatility.   
Python comes with a standard library of modules, which includes a wide range of functionality including date and time functions.

We'll create a program that will prompt a user for their birthday and calculate how many days old they are.

First we need to import the `datetime` module into the program. By importing the module, the classes and functions are available for use in the current program.

The `datetime` module supplies classes for working with dates and times. It includes the datetime class, which represents a date and time object.   

#### Here is the complete program:
~~~
from datetime import datetime

while True:
    month = input("What month were you born? (Use 1-12 for the month) ")
    if month.isdigit() and 1 <= int(month) <= 12:
        month = int(month)
        break
    else:
        print("Invalid month entered. Enter a number between 1 and 12.")

while True:
  day = (input("What day were you born? "))
  if day.isdigit() and int(day) in range(1,32):
    day = int(day)
    break
  else:
    print("Invalid day entered. Enter a number between 1 and 31")

while True:
  year = input("What year were you born? ")
  today_year = datetime.today().year
  if year.isdigit() and int(year) in range(1, datetime.now().year + 1):
    year = int(year)
    break
  else:
   print(f"Invalid year. Enter a year between 1 AD and {today_year}.")


birthday = datetime(year, month, day)
new_date = datetime.today() - birthday
days_old = new_date.days

if days_old < 0:
  print("You entered a birthday that hasn't happened yet!")
elif days_old == 0:
  print("You were born today! Happy Birthday!") 
else:
  print(f"You are {days_old:,} days old!")
~~~
