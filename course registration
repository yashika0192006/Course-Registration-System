#include <iostream>
#include <string>
using namespace std;

// Course class
class Course {
private:
    int code;
    string title;

public:
    Course(int c, string t) : code(c), title(t) {}

    void showCourse() {
        cout << "Course Code: " << code << ", Title: " << title << endl;
    }

    string getTitle() {
        return title;
    }

    int getCode() {
        return code;
    }
};

// Student class
class Student {
private:
    string name;
    int id;

public:
    Student(string n, int i) : name(n), id(i) {}

    void showDetails() {
        cout << "Student ID: " << id << ", Name: " << name << endl;
    }
};

// Registration class (association between Student and Course)
class Registration {
private:
    Student student;
    Course course;

public:
    Registration(Student s, Course c) : student(s), course(c) {}

    void confirm() {
        cout << "\n===== Registration Successful =====" << endl;
        student.showDetails();
        cout << "Registered in: " << course.getTitle() << endl;
        cout << "==================================" << endl;
    }
};

int main() {
   
    Course c1(101, "Database Management");
    Course c2(102, "Data Structures and Algorithms");

    
    string name;
    int id, choice;

    cout << "Enter Student Name: ";
    getline(cin, name);
    cout << "Enter Student ID: ";
    cin >> id;

    Student s1(name, id);

    
    cout << "\nAvailable Courses:\n";
    cout << "1. "; c1.showCourse();
    cout << "2. "; c2.showCourse();

    cout << "\nEnter course number (1 or 2): ";
    cin >> choice;

    if (choice == 1) {
        Registration reg(s1, c1);
        reg.confirm();
    } else if (choice == 2) {
        Registration reg(s1, c2);
        reg.confirm();
    } else {
        cout << "Invalid choice! Registration failed.Try again!." << endl;
    }

    return 0;
}

