# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
SQL> CREATE TABLE customers (Cust_id number,Cust_name varchar(20),Cust_addr varchar(20),mobile number);
```
### inserting the values:
```
SQL> insert into customers values(101,'Vasu','Chennai',9999999999);
SQL> insert into customers values(102,'Sri','Trichy',8888888888);
SQL> insert into customers values(103,'Deepika','London',777777777);
```
### PLSQL Cursor code
```
SQL> set serveroutput on
SQL> declare
          cursor Cust_Cursor is
          select Cust_id, Cust_name,Cust_addr,mobile
          from customers;
          Cust_id number;
          Cust_name varchar(90);
          Cust_addr varchar(90);
          mobile number;
          landline number;
          begin
          open Cust_Cursor;
          loop
          fetch Cust_Cursor into Cust_id,Cust_name,Cust_addr,mobile;
          exit when Cust_Cursor%notfound;
          dbms_output.put_line('Customer ID: '||Cust_id);
          dbms_output.put_line('Customer Name: '||Cust_name);
          dbms_output.put_line('Address: '||Cust_addr);
          dbms_output.put_line('Mobile Number: '||mobile);
          end loop;
          close Cust_cursor;
          end;
   /
```

### Output:

![sql8](https://github.com/vasundrasriravi/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393983/465aefdd-cd8c-4b29-8676-ad220d9cb66f)

![sql9](https://github.com/vasundrasriravi/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393983/46a24c59-58e0-4be1-8ad7-968dd687d7c6)

### Result:
Thus a cursor is created using PL/SQL successfully.
