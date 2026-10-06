# ==========================================
# PROJECT 01 - STUDENT MANAGEMENT SYSTEM
# ==========================================

import json

# File where student records will be saved
FILE_NAME = "students.json"


# ------------------------------------------
# Load students from file
# ------------------------------------------
def load_students():
    try:
        with open(FILE_NAME, "r") as file:
            return json.load(file)
    except FileNotFoundError:
        return []


# ------------------------------------------
# Save students to file
# ------------------------------------------
def save_students(students):
    with open(FILE_NAME, "w") as file:
        json.dump(students, file, indent=4)

    print("\nRecords saved successfully!")


# ------------------------------------------
# Add a new student
# ------------------------------------------
def add_student(students):

    student_id = input("Enter Student ID: ")

    # Check if ID already exists
    for student in students:
        if student["id"] == student_id:
            print("Student ID already exists!")
            return

    name = input("Enter Student Name: ")
    age = int(input("Enter Age: "))
    course = input("Enter Course: ")

    marks1 = float(input("Enter marks in Subject 1: "))
    marks2 = float(input("Enter marks in Subject 2: "))
    marks3 = float(input("Enter marks in Subject 3: "))

    student = {
        "id": student_id,
        "name": name,
        "age": age,
        "course": course,
        "marks": [marks1, marks2, marks3]
    }

    students.append(student)

    print("\nStudent added successfully!")


# ------------------------------------------
# Display all students
# ------------------------------------------
def display_students(students):

    if len(students) == 0:
        print("\nNo student records found.")
        return

    print("\n========== STUDENT RECORDS ==========")

    for student in students:

        average = sum(student["marks"]) / len(student["marks"])

        print("\nStudent ID :", student["id"])
        print("Name       :", student["name"])
        print("Age        :", student["age"])
        print("Course     :", student["course"])
        print("Marks      :", student["marks"])
        print("Average    :", round(average, 2))

    print("\n=====================================")


# ------------------------------------------
# Search student
# ------------------------------------------
def search_student(students):

    student_id = input("Enter Student ID to search: ")

    for student in students:

        if student["id"] == student_id:

            average = sum(student["marks"]) / len(student["marks"])

            print("\nStudent Found!")
            print("-------------------------")
            print("Student ID :", student["id"])
            print("Name       :", student["name"])
            print("Age        :", student["age"])
            print("Course     :", student["course"])
            print("Marks      :", student["marks"])
            print("Average    :", round(average, 2))

            return

    print("\nStudent not found.")


# ------------------------------------------
# Update student record
# ------------------------------------------
def update_student(students):

    student_id = input("Enter Student ID to update: ")

    for student in students:

        if student["id"] == student_id:

            print("\nStudent found.")
            print("Press Enter if you don't want to change a value.")

            name = input("Enter new name: ")
            age = input("Enter new age: ")
            course = input("Enter new course: ")

            if name != "":
                student["name"] = name

            if age != "":
                student["age"] = int(age)

            if course != "":
                student["course"] = course

            print("\nUpdate marks:")
            print("Current marks:", student["marks"])

            change_marks = input(
                "Do you want to update marks? (yes/no): "
            )

            if change_marks.lower() == "yes":

                marks1 = float(input("Enter Subject 1 marks: "))
                marks2 = float(input("Enter Subject 2 marks: "))
                marks3 = float(input("Enter Subject 3 marks: "))

                student["marks"] = [marks1, marks2, marks3]

            print("\nStudent record updated successfully!")

            return

    print("\nStudent not found.")


# ------------------------------------------
# Delete student
# ------------------------------------------
def delete_student(students):

    student_id = input("Enter Student ID to delete: ")

    for student in students:

        if student["id"] == student_id:

            students.remove(student)

            print("\nStudent deleted successfully!")

            return

    print("\nStudent not found.")


# ------------------------------------------
# Calculate average marks
# ------------------------------------------
def calculate_average(students):

    student_id = input("Enter Student ID: ")

    for student in students:

        if student["id"] == student_id:

            average = sum(student["marks"]) / len(student["marks"])

            print("\nStudent Name :", student["name"])
            print("Marks        :", student["marks"])
            print("Average Marks:", round(average, 2))

            return

    print("\nStudent not found.")


# ------------------------------------------
# Main Menu
# ------------------------------------------
def main():

    students = load_students()

    while True:

        print("\n")
        print("======================================")
        print("       STUDENT MANAGEMENT SYSTEM")
        print("======================================")

        print("1. Add Student")
        print("2. Display Students")
        print("3. Search Student")
        print("4. Update Student")
        print("5. Delete Student")
        print("6. Calculate Average Marks")
        print("7. Save Records")
        print("8. Exit")

        print("======================================")

        choice = input("Enter your choice (1-8): ")

        if choice == "1":
            add_student(students)

        elif choice == "2":
            display_students(students)

        elif choice == "3":
            search_student(students)

        elif choice == "4":
            update_student(students)

        elif choice == "5":
            delete_student(students)

        elif choice == "6":
            calculate_average(students)

        elif choice == "7":
            save_students(students)

        elif choice == "8":

            # Automatically save before exiting
            save_students(students)

            print("\nThank you for using Student Management System!")
            break

        else:
            print("\nInvalid choice! Please enter a number from 1 to 8.")


# ------------------------------------------
# Run the program
# ------------------------------------------
if __name__ == "__main__":
    main()
