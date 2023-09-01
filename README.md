# ICP3
ICP3
#!/usr/bin/env python
# coding: utf-8

# In[1]:


## Task 1 
#author: Samudrala Bindu
class Employee:
    # Class variable to count the number of Employees
    num_employees = 0

    def __init__(self, name, family, salary, department):
        self.name = name
        self.family = family
        self.salary = salary
        self.department = department
        Employee.num_employees += 1

    def display_employee_info(self):
        print(f"Name: {self.name}")
        print(f"Family: {self.family}")
        print(f"Salary: {self.salary}")
        print(f"Department: {self.department}")

    @classmethod
    def average_salary(cls, employees):
        total_salary = sum(employee.salary for employee in employees)
        return total_salary / len(employees)

class FulltimeEmployee(Employee):
    def __init__(self, name, family, salary, department, experience):
        super().__init__(name, family, salary, department)
        self.experience = experience

    def display_employee_info(self):
        super().display_employee_info()
        print(f"Experience: {self.experience} years")

# Create instances of Employee class
employee1 = Employee("John Doe", "Spouse", 60000, "HR")
employee2 = Employee("Jane Doe", "Child", 40000, "Finance")
employee3 = Employee("Bob Smith", "Spouse", 70000, "IT")

# Create instances of FulltimeEmployee class
fulltime_employee1 = FulltimeEmployee("Alice Johnson", "Spouse", 80000, "Engineering", 5)
fulltime_employee2 = FulltimeEmployee("Eve Johnson", "Child", 45000, "Marketing", 2)

# Display employee information
print("Employee Information:")
employee1.display_employee_info()
employee2.display_employee_info()
employee3.display_employee_info()

print("\nFulltime Employee Information:")
fulltime_employee1.display_employee_info()
fulltime_employee2.display_employee_info()

# Calculate and display the average salary for all employees
employees = [employee1, employee2, employee3, fulltime_employee1, fulltime_employee2]
average_salary = Employee.average_salary(employees)
print(f"\nAverage Salary for All Employees: ${average_salary:.2f}")


# In[2]:


## Task 2 
#author: Samudrala Bindu
import numpy as np

# Create a random vector of size 20 with floats in the range 1-20
random_vector = np.random.uniform(1, 20, 20)

# Reshape the array to a 4x5 matrix
reshaped_array = random_vector.reshape(4, 5)

# Find the indices of the maximum values in each row
max_indices = np.argmax(reshaped_array, axis=1)

# Replace the maximum value in each row with 0
reshaped_array[np.arange(4), max_indices] = 0

# Print the original and modified arrays
print("Original Array:")
print(random_vector)

print("\nReshaped Array:")
print(reshaped_array)






