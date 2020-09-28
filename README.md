# Python-Student-Loan-Calculator
'''
Use this to calculate total student loans, and determine how much you will owe at the end of your education! 
'''

#Part A: Calculating total amount owed after graduation (2 points)
loan_per_year = float(input('Loan Amount Per Year: '))
interest_rate = float(input('Interest Rate: '))
years = int(input('Number of Years: '))
counter = 0
total_owed = 0
while counter<years:
    counter += 1
    Interest = (loan_per_year +total_owed)*interest_rate
    total_owed = loan_per_year + total_owed + Interest
    if counter == years:
        break
print("Total owed at graduation")
print("$",total_owed)
#Part B: Determine if monthly payment is feasible (1 point)
monthly_payment = float(input('Name a monthly payment: '))
min_payment = (interest_rate*total_owed)/12
if min_payment < monthly_payment:
	print("A monthly payment of $",monthly_payment,"will work!")
else: 
	print("A monthly payment of $",monthly_payment, "won’t work! You’ll be paying off your loans forever!")
print('The minimum monthly payment for this loan would be $',min_payment)
#Part C: Determine how long it will take to pay off your student loans (2 points)
month = 0
while (total_owed > 0):
    total_owed = total_owed - monthly_payment + ((interest_rate*total_owed)/12)
    month += 1
    if total_owed == 0:
        break
print("It will take ",month,"months to pay off your student loans")
print("It will take ",month/12,"years to pay off your student loans")
