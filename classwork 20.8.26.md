QNO.1
import numpy as np
marks = np.array(list(map(int, input("Enter 5 marks: ").split())))
print("Average:", np.mean(marks))
print("Highest:", np.max(marks))
print("Lowest:", np.min(marks))

IP :78 65 92 55 84
OP: Average: 74.8
Highest: 92
Lowest: 55

QNO.2
import numpy as np
temp = np.array(list(map(int, input("Enter temperature values: ").split())))
temp[temp < 0] = 0
print("Modified temperatures:", temp)

IP:25 -3 28 -1 30 27 -5
OP:Modified temperatures: [25  0 28  0 30 27  0]

QNO.3
import numpy as np
test1 = np.array(list(map(int, input("Enter Test 1 marks: ").split())))
test2 = np.array(list(map(int, input("Enter Test 2 marks: ").split())))
students = np.where(test2 > test1)[0]
print("Students improved:", students)

IP: Test 1: 65 80 72 90 55
Test 2: 70 75 78 85 60
OP: Students improved: [0 2 4]

QN0.4
import numpy as np
matrix = np.array([
    list(map(int, input().split())),
    list(map(int, input().split())),
    list(map(int, input().split()))
])
print("Row sums:", np.sum(matrix, axis=1))
print("Column sums:", np.sum(matrix, axis=0))

IP:1 2 3
4 5 6
7 8 9
OP: Row sums: [ 6 15 24]
Column sums: [12 15 18]

QNO.5
import numpy as np
rainfall = np.array(list(map(int, input("Enter rainfall for 12 months: ").split())))
total = np.sum(rainfall)
average = np.mean(rainfall)
months = np.where(rainfall > average)[0] + 1
print("Total Rainfall:", total)
print("Average Rainfall:", round(average, 2))
print("Months having rainfall above average:", months)

IP:120 85 150 200 175 90 110 160 210 180 95 130
OP:Total Rainfall: 1705
Average Rainfall: 142.08
Months having rainfall above average: [ 3  4  5  8  9 10]

QNO.6
import pandas as pd
data = {
    'Name': ['Arun', 'Bala', 'Charan', 'Divya'],
    'Python': [80, 65, 90, 75],
    'Java': [85, 70, 88, 80],
    'DBMS': [75, 60, 92, 78]
}
df = pd.DataFrame(data)
df['Total'] = df[['Python', 'Java', 'DBMS']].sum(axis=1)
df['Average'] = df[['Python', 'Java', 'DBMS']].mean(axis=1)
print("Student Details:")
print(df[['Name', 'Total', 'Average']].to_string(index=False, float_format='%.2f'))
print("\nStudents with Average > 75:")
result = df[df['Average'] > 75]
print(result[['Name', 'Average']].to_string(index=False, float_format='%.2f'))

OP: Student Details:
  Name  Total  Average
  Arun    240    80.00
  Bala    195    65.00
Charan    270    90.00
 Divya    233    77.67

Students with Average > 75:
  Name  Average
  Arun    80.00
Charan    90.00
 Divya    77.67

 QNO.7
 import pandas as pd
data = {
    'ID': [101, 102, 103, 104, 105],
    'Name': ['Ravi', 'Kumar', 'Anu', 'Priya', 'Manoj'],
    'Department': ['IT', 'HR', 'IT', 'HR', 'Sales'],
    'Salary': [50000, 45000, 65000, 55000, 60000]
}
df = pd.DataFrame(data)
result = df.loc[df.groupby('Department')['Salary'].idxmax()]
result = result.sort_values('Department')
print(result[['Department', 'Name', 'Salary']].to_string(index=False))

 OP: Department  Name  Salary
        HR Priya   55000
        IT   Anu   65000
     Sales Manoj   60000

     QNO.8
     import pandas as pd
data = {
    'Product': ['Laptop', 'Mouse', 'Keyboard', 'Mobile', 'Tablet'],
    'Category': ['Electronics', 'Accessories', 'Accessories',
                 'Electronics', 'Electronics'],
    'Quantity': [5, 20, 10, 8, 6],
    'Price': [50000, 500, 1000, 20000, 15000]
}
df = pd.DataFrame(data)
df['Total_Sales'] = df['Quantity'] * df['Price']
print("Product Sales:")
print(df[['Product', 'Total_Sales']].to_string(index=False))
print("\nCategory-wise Total Sales:")
category_sales = df.groupby('Category')['Total_Sales'].sum()
print(category_sales.to_string())

OP: Product Sales:
 Product  Total_Sales
  Laptop       250000
   Mouse        10000
Keyboard        10000
  Mobile       160000
  Tablet        90000

Category-wise Total Sales:
Category
Accessories     20000
Electronics    500000

QNO.9
import pandas as pd
data = {
    'Name': ['Arun', 'Bala', 'Charan', 'Divya'],
    'Total_Days': [50, 50, 50, 50],
    'Present_Days': [45, 38, 48, 35]
}
df = pd.DataFrame(data)
df['Attendance %'] = (df['Present_Days'] / df['Total_Days']) * 100
print("Student Attendance:")
print(df[['Name', 'Attendance %']].to_string(index=False))
print("\nStudents below 80%:")
result = df[df['Attendance %'] < 80]
print(result[['Name', 'Attendance %']].to_string(index=False))

OP: Student Attendance:
  Name  Attendance %
  Arun          90.0
  Bala          76.0
Charan          96.0
 Divya          70.0

Students below 80%:
 Name  Attendance %
 Bala          76.0
Divya          70.0

QNO.10
import pandas as pd
data = {
    'Product': ['Laptop', 'Mobile', 'Mouse', 'Keyboard', 'Tablet'],
    'Category': ['Electronics', 'Electronics', 'Accessories',
                 'Accessories', 'Electronics'],
    'Rating': [4.5, 4.2, 3.8, 4.6, 4.8]
}
df = pd.DataFrame(data)
average_rating = df.groupby('Category')['Rating'].mean()
print("Average Rating by Category:")
print(average_rating.to_string(float_format='%.2f'))
highest_category = average_rating.idxmax()
highest_rating = average_rating.max()
print("\nHighest Rated Category:")
print(highest_category, f"{highest_rating:.2f}")

OP: Average Rating by Category:
Category
Accessories    4.20
Electronics    4.50
Highest Rated Category:
Electronics 4.50
