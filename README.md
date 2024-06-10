# DS
.............................
This repo contains assignment solutions , ppt upto 8 , major project.

.     
[10/06, 8:17 am] Shohail..</>: import matplotlib.pyplot as plt

# Dataset
experience = [48, 32, 10, 39, 50, 80, 6, 20, 96, 99]
salary = [35124, 79213, 79216, 48000, 10023, 28800, 32400, 45500, 21230, 31240]

# Creating the scatter plot
plt.scatter(experience, salary, color='blue', marker='o')

# Adding the title and labels
plt.title("Experience vs. Salary")
plt.xlabel("Experience (in months)")
plt.ylabel("Salary (in rupees)")

# Setting the range for the x-axis
plt.xlim(0, 100)

# Display the plot
plt.show()
[10/06, 8:22 am] Shohail..</>: import math

# Dataset
salary = [35124, 79213, 79216, 48000, 10023, 28800, 32400, 45500, 21230, 31240]

# Function to calculate the median
def calculate_median(data):
    sorted_data = sorted(data)
    n = len(sorted_data)
    mid = n // 2
    
    if n % 2 == 0:
        median = (sorted_data[mid - 1] + sorted_data[mid]) / 2
    else:
        median = sorted_data[mid]
    
    return median

# Function to calculate the standard deviation
def calculate_std_deviation(data):
    n = len(data)
    mean = sum(data) / n
    squared_diff = [(x - mean) ** 2 for x in data]
    variance = sum(squared_diff) / n
    std_deviation = math.sqrt(variance)
    
    return std_deviation

# Compute the median
median_salary = calculate_median(salary)

# Compute the standard deviation
std_deviation_salary = calculate_std_deviation(salary)

median_salary, std_deviation_salary
[10/06, 9:20 am] Shohail..</>: def diff_quotient(f, x, y, z, h, var):
    if var == 'x':
        return (f(x + h, y, z) - f(x, y, z)) / h
    elif var == 'y':
        return (f(x, y + h, z) - f(x, y, z)) / h
    elif var == 'z':
        return (f(x, y, z + h) - f(x, y, z)) / h
    else:
        raise ValueError("Variable must be 'x', 'y', or 'z'")

def f(x, y, z):
    return x**2 + y**2 + z**2

def gradient(f, x, y, z, h=1e-5):
    partial_x = diff_quotient(f, x, y, z, h, 'x')
    partial_y = diff_quotient(f, x, y, z, h, 'y')
    partial_z = diff_quotient(f, x, y, z, h, 'z')
    return [partial_x, partial_y, partial_z]

# Example usage
x, y, z = 1.0, 2.0, 3.0
grad = gradient(f, x, y, z)
print(f"The gradient of f(x, y, z) at (x, y, z) = ({x}, {y}, {z}) is {grad}")
