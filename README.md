print("---Welcome to Mark's Coffee---")
find_menu = 0 #ตัวแปรสำหรับเข้าลูป while เพื่อเลือกMenu
find_coffee = False #ตัวแปรสำหรับเข้าลูป while เพื่อเลืกเมนูกาแฟ
find_type_coffee = False #ตัวแปรสำหรับเข้าลูป while เพื่อเลือกว่าต้องการกาแฟประเภทไหน
while find_menu <= 0:
    choose_menu = input("Please type 1 to show menu: ")
    if choose_menu == "1":
        find_menu += 1
        print("""---Choose the menu---
        1. Espresso
        2. Cappuccino
        3. Latte""")
        while find_coffee == False:
            menu = input("Select Coffee: ")
            if menu == "1" or menu == "Espresso" or menu == "espresso": #กรณีเลือกเมนูกาแฟ 1
                print("""You chose Espresso coffee
            ---Choose the type of the coffee---
                1. Hot 55 baht
                2. Cold 60 baht""")
                find_coffee = True
                while find_type_coffee == False:
                    type_coffee = (input("Please choose hot or cold coffee.: ")) #ผู้ใช้เลือประเภทของกาแฟ
                    if type_coffee == "1" or type_coffee == "Hot" or type_coffee == "hot" or type_coffee == "55": #ผู้ใช้เลือกาแฟร้อน
                        print("---You chose hot Espresso 55 baht---")
                        result = 0
                        change = 0
                        while True: #ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %.f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %.f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                ---Please try again---""")
                                else:
                                    print("Error")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                for i in money:
                                    if i in range()
                                if money > 55: #กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht"% result)
                                    print("---Thank you---")
                                    break
                                elif money == 55: #กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0: #กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht"% result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0: #กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0: #กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55: #กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55: #กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0: #กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                        ---Please try again---""")
                            elif money.isalpha(): #กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else: #กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    elif type_coffee == "2" or type_coffee == "Cold" or type_coffee == "cold" or type_coffee == "60": #ผู้ใช้เลือกาแฟเย็น
                        print("---You chose cold Espresso 60 baht---")
                        result = 0
                        change = 0
                        while True:  # ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f%f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif money.isalpha():  # กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else:  # กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    else: #กรณีใส่ข้อมูลประเภทกาแฟผิด
                        print("""Sorry, your choice is incorrect. Please try again.
                    Type includes
                    1. Hot 55 baht
                    2. Cold 60 baht""")
            elif menu == "2" or menu == "Cappuccino" or menu == "cappuccino": #กรณีเลือกเมนูกาแฟ 2
                print("""You chose Cappuccino coffee
            ---Choose the type of the coffee---
                1. Hot 55 baht
                2. Cold 60 baht""")
                find_coffee = True
                while find_type_coffee == False:
                    type_coffee = (input("Please choose hot or cold coffee.: ")) #ผู้ใช้เลือประเภทของกาแฟ
                    if type_coffee == "1" or type_coffee == "Hot" or type_coffee == "hot" or type_coffee == "55": #ผู้ใช้เลือกาแฟร้อน
                        print("---You chose hot Cappuccino 55 baht---")
                        result = 0
                        change = 0
                        while True:  # ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif money.isalpha():  # กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else: #กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    elif type_coffee == "2" or type_coffee == "Cold" or type_coffee == "cold" or type_coffee == "60": #ผู้ใช้เลือกาแฟเย็น
                        print("---You chose cold Cappuccino 60 baht---")
                        result = 0
                        change = 0
                        while True:  # ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif money.isalpha():  # กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else: #กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    else: #กรณีใส่ข้อมูลประเภทกาแฟผิด
                        print("""Sorry, your choice is incorrect. Please try again.
                    Type includes
                    1. Hot 55 baht
                    2. Cold 60 baht""")
            elif menu == "3" or menu == "Latte" or menu == "latte": #กรณีเลือกเมนูกาแฟ 3
                print("""You chose Latte coffee
            ---Choose the type of the coffee---
                1. Hot 55 baht
                2. Cold 60 baht""")
                find_coffee = True
                while find_type_coffee == False:
                    type_coffee = (input("Please choose hot or cold coffee.: ")) #ผู้ใช้เลือประเภทของกาแฟ
                    if type_coffee == "1" or type_coffee == "Hot" or type_coffee == "hot" or type_coffee == "55": #ผู้ใช้เลือกาแฟร้อน
                        print("---You chose hot Latte 55 baht---")
                        result = 0
                        change = 0
                        while True:  # ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                if money > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 55
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 55 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 55:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 55 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 55:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 55:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 55
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif money.isalpha():  # กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else: #กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    elif type_coffee == "2" or type_coffee == "Cold" or type_coffee == "cold" or type_coffee == "60": #ผู้ใช้เลือกาแฟเย็น
                        print("---You chose cold Latte 60 baht---")
                        result = 0
                        change = 0
                        while True:  # ลูปคำนวนเงิน
                            money = (input("Input your money: "))
                            if money.isdigit(): #กรณีท่ี่ผู้ใช้กรอกจำนวนเงินโดยที่ไม่มีทศนิยม
                                money = int(money)
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f%f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "." in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย dot . หรือทศนิยม ภายใน input
                                money = int(money.split(".")[0])
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif "," in money: # กรณทีผู้ใช้กรอกจำนวนเงินโดยมีเครื่องหมาย Comma , ภายใน input
                                money = int(money.replace(",", ""))
                                if money > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    print("You received a change of %f baht" % result)
                                    print("---Thank you---")
                                    break
                                elif money == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้
                                    money -= 60
                                    result += money
                                    if result > 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    elif result == 0:  # กรณีที่มีเงินทอนในครั้งแรก แต้ต่อมากลับใส่ครบพอดี และไม่มีเงินทอนแล้ว
                                        print("---Thank you---")
                                        break
                                elif money < 60 and money >= 0:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้
                                    result += money
                                    if result < 60:  # กรณีที่เงินน้อยกว่าราคาที่ตั้งไว้ ถึงแม้ว่าจะใส่เข้าไปเพิ่มแล้ว
                                        change = 60 - result
                                        print(
                                            f"Insufficient funds. Please top up your balance with {change} baht and try again. ")
                                    elif result == 60:  # กรณีที่เงินเท่ากับราคาที่ตั้งไว้หลังจากที่เรามีการใส่เข้าไปเพิ่ม
                                        print("---Thank you---")
                                        break
                                    elif result > 60:  # กรณีที่เงินมากกว่าราคาที่ตั้งไว้หลังจากที่เราใส่เพิ่มเข้าไป
                                        result -= 60
                                        print("You received a change of %f baht" % result)
                                        print("---Thank you---")
                                        break
                                    else:  # กรณีผู้ใช้ใส่ข้อมูลผิดหลังจากใส่เงินเพิ่มเข้าไปจากราคาตอนแรกที่ยังขาดอยู่
                                        print("Invalid input! Please enter money value only.")
                                elif money < 0:  # กรณีที่เงินติดลบ
                                    print("""Negative amount entered. Please enter a positive number.
                                               ---Please try again---""")
                            elif money.isalpha():  # กรณีผู้ใช้ใส่ข้อมูลผิด
                                print("Invalid input! Please enter money value only.")
                            else: #กรณีเงินติดลบ
                                print("Negative amount entered. Please enter a positive number")
                        find_type_coffee = True
                    else: #กรณีใส่ข้อมูลประเภทกาแฟผิด
                        print("""Sorry, your choice is incorrect. Please try again.
                    Type includes
                    1. Hot 55 baht
                    2. Cold 60 baht""")
            else: #กรณีทีพิมพ์ผิด หรือไม่มีเมนูที่เลือก
                print("""Sorry, your choice is incorrect. Please try again.
            ---Menu includes--- 
                1. Espresso
                2. Cappuccino
                3. Latte""")
    else:
        print("Please try again!")
