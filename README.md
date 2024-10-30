# StudentGradeTracker
Your Java program for a Student Grade Tracker is well-structured and readable. Here are some suggestions for improvement:

1. Variable Naming: Variable names like grades and currentGrades are confusing. Consider renaming them to allGrades and studentGrades.
2. Method Signature: The addNewGrade and modifyGrade methods modify the original array. Consider returning the modified array instead of modifying it directly.
3. Error Handling: In modifyGrade, check if the index is within the bounds of non-zero elements, not the entire array.
4. Code Duplication: The Scanner object is created multiple times. Consider creating it once and passing it as a parameter to methods.
5. Magic Numbers: Replace magic numbers (e.g., 5 in int[] grades = new int[5];) with named constants.

Here's the refactored code:


package CodeAlphaProject;

import java.util.Scanner;

public class StudentGradeTracker {

    private static final int INITIAL_GRADE_CAPACITY = 5;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] studentGrades = {85, 92, 78, 95, 88};

        System.out.println("Welcome to the Student Grade Tracker!");

        int choice;
        do {
            System.out.println("\nCurrent Grades:");
            printGrades(studentGrades);

            System.out.println("\nOptions:");
            System.out.println("1. Add a new grade");
            System.out.println("2. Modify an existing grade");
            System.out.println("3. Display current grades");
            System.out.println("4. Exit");

            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case
