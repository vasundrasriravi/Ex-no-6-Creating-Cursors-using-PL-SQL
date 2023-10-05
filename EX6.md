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



### Result:
Thus a cursor is created using PL/SQL successfully.
