# dates and Times

The **datetime module** in Python is a powerful module that provides classes for working with dates and times. It is part of the Python standard library and is widely used for various applications involving time-related operations. Here's a brief overview of the primary classes and functionalities provided by the **datetime** module.

## Key Classes in the datetime Module:

**1. 'datetime Class:'**

+ Represents a date and a time.
+ Attributes: **year, month, day, hour, minute, second, microsecond.**

```python
from datetime import datetime

current_datetime = datetime.now()
print(current_datetime)
```
**2. date Class:**

+ Represents a date (year, month, day).
+ Useful for operations that only involve the date, without considering the time.
```python
from datetime import date

today = date.today()
print(today)
```

**3. time Class:**
+ Represents a time (hour, minute, second, microsecond).
+ Useful for operations that only involve the time, without considering the date.
```python
from datetime import time

current_time = time(12, 30, 0)
print(current_time)
```

**4. timedelta Class:**

+ Represents the difference between two dates or times.
+ Useful for performing arithmetic operations on dates and times.
```python
from datetime import datetime, timedelta

current_datetime = datetime.now()
future_datetime = current_datetime + timedelta(days=7)
print(future_datetime)
```

## Formatting and Parsing Dates:
The **strftime** method is used to format dates as strings, and **strptime** is used to parse strings into **datetime** objects.

```python
from datetime import datetime

current_datetime = datetime.now()

# Format datetime as a string
formatted_date = current_datetime.strftime("%Y-%m-%d %H:%M:%S")
print(formatted_date)

# Parse a string into a datetime object
parsed_datetime = datetime.strptime("2023-11-12 15:30:00", "%Y-%m-%d %H:%M:%S")
print(parsed_datetime)

```