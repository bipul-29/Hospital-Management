# Hospital-Management
Hospital Management System
CODE:

# Hospital Management System (Simple Version)

patients = []
appointments = []
bills = []

while True:
    print("\n--- Hospital Management System ---")
    print("1. Add Patient")
    print("2. View Patients")
    print("3. Book Appointment")
    print("4. View Appointments")
    print("5. Generate Bill")
    print("6. View Bills")
    print("7. Exit")

    choice = int(input("Enter your choice: "))

    # Add Patient
    if choice == 1:
        name = input("Enter patient name: ")
        age = int(input("Enter age: "))
        disease = input("Enter disease: ")

        patient = [name, age, disease]
        patients.append(patient)

        print("Patient added successfully!")

    # View Patients
    elif choice == 2:
        if len(patients) == 0:
            print("No patients found")
        else:
            print("\n--- Patient Details ---")
            for i in range(len(patients)):
                print("ID:", i, "| Name:", patients[i][0], "| Age:", patients[i][1], "| Disease:", patients[i][2])

    # Book Appointment
    elif choice == 3:
        pid = int(input("Enter patient ID: "))

        if pid >= len(patients):
            print("Invalid patient ID")
        else:
            date = input("Enter appointment date: ")
            appointment = [pid, date]
            appointments.append(appointment)

            print("Appointment booked for", patients[pid][0])

    # View Appointments
    elif choice == 4:
        if len(appointments) == 0:
            print("No appointments found")
        else:
            print("\n--- Appointments ---")
            for a in appointments:
                pid = a[0]
                name = patients[pid][0]
                print("Patient Name:", name, "| Date:", a[1])

    # Generate Bill
    elif choice == 5:
        pid = int(input("Enter patient ID: "))

        if pid >= len(patients):
            print("Invalid patient ID")
        else:
            amount = float(input("Enter amount: "))
            bill = [pid, amount]
            bills.append(bill)

            print("Bill generated for", patients[pid][0])

    # View Bills
    elif choice == 6:
        if len(bills) == 0:
            print("No bills found")
        else:
            print("\n--- Bills ---")
            for b in bills:
                pid = b[0]
                name = patients[pid][0]
                print("Patient Name:", name, "| Amount:", b[1])

    # Exit
    elif choice == 7:
        print("Exiting program...")
        break

    else:
        print("Invalid choice")
