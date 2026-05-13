# Practice_programming_Menu_Coffee-
# ผมกำลังฝึกเขียน Program Python เกี่ยวกับร้านกาแฟแห่งหนึ่ง
print("""---Welcome to Mark's Coffee---
Please type 1 to show menu: 1
---Choose the menu---
1. Espresso
2. Cappucino
3. Latte""")
menu = int(input("Select coffee: "))
if menu == 1:
    print("""---Choose the type of the coffee---
    1. Hot 55 baht
    2. Cold 60 baht""")
    type_coffee = int(input("Select type: "))
    if type_coffee == 1:
        print("---You chose hot Espresso 55 baht---")
        money = int(input("Input your money: "))
        if money > 55:
            money -= 55
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 55:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
    elif type_coffee == 2:
        print("---You chose cold Espresso 60 baht---")
        money = int(input("Input your money: "))
        if money > 60:
            money -= 60
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 60:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
elif menu == 2:
    print("""---Choose the type of the coffee---
    1. Hot 55 baht
    2. Cold 60 baht""")
    type_coffee = int(input("Select type: "))
    if type_coffee == 1:
        print("---You chose hot Cappucino 55 baht---")
        money = int(input("Input your money: "))
        if money > 55:
            money -= 55
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 55:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
    elif type_coffee == 2:
        print("---You chose cold Cappucino 60 baht---")
        money = int(input("Input your money: "))
        if money > 60:
            money -= 60
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 60:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
elif menu == 3:
    print("""---Choose the type of the coffee---
    1. Hot 55 baht
    2. Cold 60 baht""")
    type_coffee = int(input("Select type: "))
    if type_coffee == 1:
        print("---You chose hot Latte 55 baht---")
        money = int(input("Input your money: "))
        if money > 55:
            money -= 55
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 55:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
    elif type_coffee == 2:
        print("---You chose cold Latte 60 baht---")
        money = int(input("Input your money: "))
        if money > 60:
            money -= 60
            print("You recieved a change of %d baht"% money)
            print("---Thank you---")
        elif money == 60:
            print("---Thank you---")
        else:
            print("""Not enough money
---Please try again---""")
else:
    print("Sorry, something went wrong")
