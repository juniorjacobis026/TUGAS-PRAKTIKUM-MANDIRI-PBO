class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

class Company:
    def __init__(self):
        self.__employees = []

    def add_employee(self, employee):
        if isinstance(employee, Employee):
            self.__employees.append(employee)
            print(f"Berhasil: {employee.name} ditambahkan.")
        else:
            print("Gagal: Input bukan object Employee.")

    def __calculate_payroll(self):
        total_payroll = sum(emp.salary for emp in self.__employees)
        return total_payroll

    def generate_payroll_report(self):
        total = self.__calculate_payroll()
        print(f"Total Payroll: Rp{total}")

if __name__ == "__main__":
    my_company = Company()

    emp1 = Employee("Andi", 5000000)
    emp2 = Employee("Budi", 6500000)

    my_company.add_employee(emp1)
    my_company.add_employee(emp2)
    my_company.add_employee("Siti")

    my_company.generate_payroll_report()