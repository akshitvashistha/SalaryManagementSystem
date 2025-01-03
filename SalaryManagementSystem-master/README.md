# SalaryManagementSystem
 
It's a PL/SQL project. I created this project with distributed database.
Salary Management has 3 users
1. Admin/HR
2. Accountant
3. Employee

Procedures and Functions
1. Employee
 Module
·         ViewDetails()
  Usage      : Show employee his/her details with payment history
  Parameter: EmployeeID
  Output     : Show details of given employee ID
2. Accountant
 Module
·         PaySalary()
  Usage      : Pay Employees Salaries by a function GenerateSalary() and a procedure TransectSalary() call
 Parameter: Employee ID, Month of Giving salary
 Output     :  Pay salary of given EID and month
Procedures
·         AddFund()
 Usage      : Increase fund
 Parameter: Amount
 Output     : Increase fund with given amount
·         AddLeave()
 Usage      : Add leaves of Employees of specific month
 Parameter: EID, S_month, L_days
 Output     : Add leaves of  given Employee ID, Month
·         TransectSalary()
Usage  : It’s the transection procedure for paymets use function ChechValid() and procedure UpdateFund() to complete
  Parameter: EID, amount, month
 Output     : Transection for payments
·         UpdateFund()
 Usage      : After transection the amount of payments will be reduce by this procedure
 Parameter: Amount
 Output     : Updated fund after transection
Functions
·         GenerateSalary()
 Usage      : Generate salary calculate with leaves of given month
 Parameter: EID, month
 Return     : Generated salary
·         CheckValid()
 Usage      : This says either its payable or not
 Parameter: EID, month
 Return     : 1 for valid 2 for invalid
3.      Admin
Procedures
·         AddEmployee()
 Usage      : Add new employee and assign his salary
 Parameter: Name, gender, email, joiningDate, SID
 Output     : Add the person as employee and assigned his salary
·         ChangeEmpPost()
 Usage      : Employee promote or demote
 Parameter: EID,SID
 Output     : Changed Pay Scale with given EID, SID


Triggers

AddLeaves              : Triggered if data insert into Leave table
ChangeEmpSalary  : Triggered if data update in Employee_salary Table and there is an audit table to track changes.
AddEmp                 : Triggered if data insert into Employee table
AddEmpSalary       : Triggered if new employee get assigned salary
Transect                  : Triggered when transection occurs
UpdateFund            : Triggered id data update in Fund Table and there is an audit table to track changes.

Entities 

         Employee(EID, EName, Gender, Email, JoinDate)
         Salary(SID, Basic, Allowance)
         Employee_Salary(EID(FK),  SID(FK),)
         Leave(LID, EID(FK),  L_month, L_days)
         Transection(TID, EID(FK), Amount, T_Date, S_month)
         Fund(FID, Fund_amount)
         Fund_Audit(NewFund, OldFund, T_Date)
         EmpSalary_Audit(EID, NewSID, OldSID, ChangingDate)


ER Diagram

Transparency
There are three levels of transparency in distributed database.
·         Level 1: Location Transparency
·         Level 2: Fragmentation Transparency
·         Level 3: Local Mapping Transparency
In Level 3 transparency, location and fragmentation details are available to application user. In our project we divided the data into different fragments and kept them in different locations. All fragmentations are Horizontal fragmentation based on the ID. These fragments were kept in different sites. For example:

Emp1: Select * from Employee where eid <= 5;
Emp2: Select * from Employee where eid > 5;

Implementation Steps

Implementation steps.
·         Creating an Entity Relationship Diagram
·         Creating fragments
·         Linking up all the sites.
·         Inserting data to different sites according to the fragments
·         Creating PL/SQL functions, procedures, control statement, triggers, packages
·         Testing

Conclusion
In this project, we tried to implement based on some high quality Salary Management System. We tried to give an idea how distributed database work in real life scenario. We look forward to implement the project in future on a larger scale.



