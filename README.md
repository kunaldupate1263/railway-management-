# railway-management-
railway-management-system
# Railway Management System (Mini Project)

tickets = []

def book_ticket():
    print("\n--- Book Ticket ---")
    name = input("Enter passenger name: ")
    age = input("Enter age: ")
    from_station = input("From station: ")
    to_station = input("To station: ")

    pnr = len(tickets) + 1  # simple PNR generation

    ticket = {
        "pnr": pnr,
        "name": name,
        "age": age,
        "from": from_station,
        "to": to_station
    }

    tickets.append(ticket)
    print(f"\n✅ Ticket booked successfully! Your PNR is {pnr}\n")


def view_tickets():
    print("\n--- All Tickets ---")

    if len(tickets) == 0:
        print("❌ No tickets booked yet!\n")
        return

    for t in tickets:
        print("----------------------")
        print("PNR:", t["pnr"])
        print("Name:", t["name"])
        print("Age:", t["age"])
        print("From:", t["from"])
        print("To:", t["to"])
    print("----------------------\n")


def search_ticket():
    print("\n--- Search Ticket ---")
    pnr = int(input("Enter PNR number: "))

    for t in tickets:
        if t["pnr"] == pnr:
            print("\n✅ Ticket Found!")
            print("PNR:", t["pnr"])
            print("Name:", t["name"])
            print("Age:", t["age"])
            print("From:", t["from"])
            print("To:", t["to"])
            return

    print("❌ Ticket not found!\n")


def cancel_ticket():
    print("\n--- Cancel Ticket ---")
    pnr = int(input("Enter PNR number: "))

    for t in tickets:
        if t["pnr"] == pnr:
            tickets.remove(t)
            print("✅ Ticket cancelled successfully!\n")
            return

    print("❌ Ticket not found!\n")


while True:
    print("\n==============================")
    print("🚆 Railway Management System")
    print("==============================")
    print("1. Book Ticket")
    print("2. View Tickets")
    print("3. Search Ticket")
    print("4. Cancel Ticket")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        book_ticket()
    elif choice == "2":
        view_tickets()
    elif choice == "3":
        search_ticket()
    elif choice == "4":
        cancel_ticket()
    elif choice == "5":
        print("\n🚆 Exiting System... Goodbye!")
        break
    else:
        print("❌ Invalid choice! Try again.")
    
