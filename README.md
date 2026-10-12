# student-grade-calculator
# Author: Nagalla Janardhana Rao


def calculate_grade(percentage):
    """Return a grade based on the student's percentage."""

    if percentage >= 90:
        return "A+"
    elif percentage >= 80:
        return "A"
    elif percentage >= 70:
        return "B"
    elif percentage >= 60:
        return "C"
    elif percentage >= 50:
        return "D"
    else:
        return "F"


def main():
    print("=" * 40)
    print("       STUDENT GRADE CALCULATOR")
    print("=" * 40)

    name = input("Enter student name: ").strip()

    if not name:
        print("Error: Student name cannot be empty.")
        return

    try:
        subjects = int(input("Enter number of subjects: "))

        if subjects <= 0:
            print("Error: Number of subjects must be positive.")
            return

        total_marks = 0

        for i in range(1, subjects + 1):
            while True:
                try:
                    marks = float(input(f"Enter marks for subject {i} (0-100): "))

                    if 0 <= marks <= 100:
                        total_marks += marks
                        break

                    print("Invalid marks. Enter a value between 0 and 100.")

                except ValueError:
                    print("Invalid input. Please enter a number.")

        maximum_marks = subjects * 100
        percentage = (total_marks / maximum_marks) * 100
        grade = calculate_grade(percentage)

        print("\n" + "=" * 40)
        print("           STUDENT RESULT")
        print("=" * 40)
        print(f"Student Name : {name}")
        print(f"Subjects     : {subjects}")
        print(f"Total Marks  : {total_marks:g}/{maximum_marks}")
        print(f"Percentage   : {percentage:.2f}%")
        print(f"Grade        : {grade}")
        print("=" * 40)

        if percentage >= 50:
            print("Result       : PASS")
        else:
            print("Result       : FAIL")

        print("=" * 40)


if __name__ == "__main__":
    main()
    
