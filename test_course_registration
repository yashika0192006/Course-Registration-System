#include <gtest/gtest.h>
#include <sstream>
#include <string>
#include <iostream>
using namespace std;


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


class Student {
private:
    string name;
    int id;

public:
    Student(string n, int i) : name(n), id(i) {}

    void showDetails() {
        cout << "Student ID: " << id << ", Name: " << name << endl;
    }

    string getName() { return name; }
    int getId() { return id; }
};


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

    string getCourseTitle() { return course.getTitle(); }
    int getCourseCode() { return course.getCode(); }
    string getStudentName() { return student.getName(); }
    int getStudentId() { return student.getId(); }
};



TEST(CourseTest, CheckCourseAttributes) {
    Course c1(101, "Database Management");
    EXPECT_EQ(c1.getCode(), 101);
    EXPECT_EQ(c1.getTitle(), "Database Management");
}


TEST(StudentTest, CheckStudentAttributes) {
    Student s1("Yashika", 10);
    EXPECT_EQ(s1.getName(), "Yashika");
    EXPECT_EQ(s1.getId(), 10);
}


TEST(RegistrationTest, ConfirmRegistrationData) {
    Student s1("Aarav", 11);
    Course c1(201, "Data Structures");

    Registration r(s1, c1);
    EXPECT_EQ(r.getStudentName(), "Aarav");
    EXPECT_EQ(r.getCourseTitle(), "Data Structures");
    EXPECT_EQ(r.getCourseCode(), 201);
}


TEST(RegistrationTest, ConfirmRegistrationOutput) {
    Student s1("Riya", 12);
    Course c1(301, "OOP");

    Registration r(s1, c1);

    testing::internal::CaptureStdout();
    r.confirm();
    string output = testing::internal::GetCapturedStdout();

    EXPECT_NE(output.find("Registration Successful"), string::npos);
    EXPECT_NE(output.find("Riya"), string::npos);
    EXPECT_NE(output.find("OOP"), string::npos);
}


int main(int argc, char **argv) {
    ::testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}
