#include <iostream>
using namespace std;

class Employee {
protected:
    int empId;
    string name;
    double salary;

public:
    void getEmployee() {
        cout << "Enter ID: ";
        cin >> empId;

        cout << "Enter Name: ";
        cin >> name;

        cout << "Enter Salary: ";
        cin >> salary;
    }

    void displayEmployee() {
        cout << "\nID: " << empId;
        cout << "\nName: " << name;
        cout << "\nSalary: " << salary;
    }
};

// ---------------- Developer ----------------
class Developer : public Employee {
    double bonus;

public:
    void getDeveloper() {
        getEmployee();
        cout << "Enter Bonus: ";
        cin >> bonus;
    }

    void displayDeveloper() {
        displayEmployee();
        cout << "\nBonus: " << bonus;
        cout << "\nTotal Salary: " << salary + bonus << endl;
    }
};

// ---------------- Manager ----------------
class Manager : public Employee {
    double allowance;

public:
    void getManager() {
        getEmployee();
        cout << "Enter Allowance: ";
        cin >> allowance;
    }

    void displayManager() {
        displayEmployee();
        cout << "\nAllowance: " << allowance;
        cout << "\nTotal Salary: " << salary + allowance << endl;
    }
};

int main() {
    int nDev, nMan;

    cout << "Enter number of Developers: ";
    cin >> nDev;

    cout << "Enter number of Managers: ";
    cin >> nMan;

    Developer dev[nDev];
    Manager man[nMan];

    cout << "\n--- Enter Developer Details ---\n";
    for (int i = 0; i < nDev; i++) {
        cout << "\nDeveloper " << i + 1 << endl;
        dev[i].getDeveloper();
    }

    cout << "\n--- Enter Manager Details ---\n";
    for (int i = 0; i < nMan; i++) {
        cout << "\nManager " << i + 1 << endl;
        man[i].getManager();
    }

    cout << "\n========= Developer List =========\n";
    for (int i = 0; i < nDev; i++) {
        cout << "\nDeveloper " << i + 1;
        dev[i].displayDeveloper();
    }

    cout << "\n========= Manager List =========\n";
    for (int i = 0; i < nMan; i++) {
        cout << "\nManager " << i + 1;
        man[i].displayManager();
    }

    return 0;
}
