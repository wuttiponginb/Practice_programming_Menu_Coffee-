print("---Welcome to Mark's Coffee---")

# ใช้ตัวแปรนี้ควบคุมให้ผู้ใช้พิมพ์ 1 เพื่อแสดงเมนูก่อน
find_menu = 0

while find_menu <= 0:
    choose_menu = input("Please type 1 to show menu: ").strip()

    if choose_menu == "1":
        find_menu += 1

        print("""---Choose the menu---
1. Espresso
2. Cappuccino
3. Latte""")

        # วนลูปจนกว่าผู้ใช้จะเลือกเมนูกาแฟถูกต้อง
        while True:
            menu = input("Select Coffee: ").strip().lower()

            if menu == "1" or menu == "espresso":
                coffee_name = "Espresso"
                break
            elif menu == "2" or menu == "cappuccino":
                coffee_name = "Cappuccino"
                break
            elif menu == "3" or menu == "latte":
                coffee_name = "Latte"
                break
            else:
                print("""Sorry, your choice is incorrect. Please try again.
---Menu includes---
1. Espresso
2. Cappuccino
3. Latte""")

        print(f"""You chose {coffee_name} coffee
---Choose the type of the coffee---
1. Hot 55 baht
2. Cold 60 baht""")

        # วนลูปจนกว่าผู้ใช้จะเลือกประเภทกาแฟถูกต้อง
        while True:
            type_coffee = input("Please choose hot or cold coffee: ").strip().lower()

            if type_coffee == "1" or type_coffee == "hot" or type_coffee == "55":
                coffee_type = "hot"
                price = 55
                break
            elif type_coffee == "2" or type_coffee == "cold" or type_coffee == "60":
                coffee_type = "cold"
                price = 60
                break
            else:
                print("""Sorry, your choice is incorrect. Please try again.
Type includes
1. Hot 55 baht
2. Cold 60 baht""")

        print(f"---You chose {coffee_type} {coffee_name} {price} baht---")

        total = 0.0

        # วนลูปรับเงินจนกว่าผู้ใช้จะจ่ายครบหรือเกินราคา
        while True:
            money_input = input("Input your money: ").strip()

            # ปรับเพิ่ม: ลบ comma ออกจากจำนวนเงิน เช่น 1,000 -> 1000
            money_input = money_input.replace(",", "")

            # ปรับเพิ่ม: ตรวจว่าข้อมูลเป็นตัวเลขจริงหรือไม่
            # เช่น 50dsf, abc50, 10baht จะเข้า except และแจ้งว่าให้กรอกตัวเลขเท่านั้น
            try:
                money = float(money_input)
            except ValueError:
                print("Invalid input! Please enter numbers only.")
                continue

            # ปรับเพิ่ม: ตรวจกรณีผู้ใช้กรอกเงินติดลบ เช่น -10, -50.5
            if money < 0:
                print("Negative amount entered. Please enter a positive number.")
                continue

            total += money

            # กรณีที่เงินยังไม่พอ ให้บอกจำนวนเงินที่ยังขาด
            if total < price:
                remaining = price - total
                print(f"Insufficient funds. Please top up your balance with {remaining:.2f} baht and try again.")

            # กรณีที่เงินพอดีกับราคา
            elif total == price:
                print("---Thank you---")
                break

            # กรณีที่เงินมากกว่าราคา ให้ทอนเงิน
            else:
                change = total - price

                # ปรับเพิ่ม: แสดงเงินทอนเป็นทศนิยม 2 ตำแหน่ง
                # แก้ปัญหาเดิมที่ใช้ %f แล้วแสดงเป็น 945.000000
                print(f"You received a change of {change:.2f} baht")
                print("---Thank you---")
                break

    else:
        print("Please try again!")
