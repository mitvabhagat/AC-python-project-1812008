# AC-python-project-1812008



name=input("Name on your bank account? ")
balance=float(input("Your current balance? "))

def printMenu():
    print("\n***Welcome to our ATM service***")
    print("\n***MENU***\nEnter 'b'(balance),\n'd'(deposit),\n'w'(withdraw),\n'q'(quit)\n")

def getTransaction():
    transaction=str(input("Enter your option: \n"))
    return transaction

def withdraw(bal,amt):
    global balance
    balance=bal-amt
    if balance<0:
        balance=balance-10

def formatCurrency(amt):
    return "Rs.%.2f" %amt

printMenu()
command=str(getTransaction())

while command!="q":
    if (command=="b"):
        print("\nYour current balance is",formatCurrency(balance))
        printMenu()
        command=str(getTransaction())
    elif (command=="d"):
        amount=float(input("\nPlease enter the Amount to deposit "))
        balance=balance+amount
        printMenu()
        command=str(getTransaction())
    elif (command=="w"):
        amount=float(input("\nPlease enter the Amount to withdraw "))
        withdraw(balance,amount)
        printMenu()
        command=str(getTransaction())
    else:
        print("\nIncorrect command. Please try again.")
        printMenu()
        command=str(getTransaction())

print("\n***Thank you! visit again!***")
