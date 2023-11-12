
https://blogs.oracle.com/sql/post/how-to-create-users-grant-them-privileges-and-remove-them-in-oracle-database

issue 1: Invalid common user or role name
alter session set "_ORACLE_SCRIPT"=true;
For more information, see: http://www.dba-oracle.com/t_ora_65096_create_user_12c_without_c_prefix.htm

# oracle-create-new-user-grant-command

create table Employee_M
(Ename varchar2(20),employee_id varchar2(20),manager_id varchar2(20));

insert into Employee_M values('Amit','1','10');							  
insert into Employee_M values('Rakesh','10','2');
insert into Employee_M values('Anmol','3','2');
insert into Employee_M values('Karbhari','2',null);							  
insert into Employee_M values('rohit','4','10');
commit;

select * from employee_m;
select ename, employee_id, manager_id, prior ename, level
from Employee_M
connect by prior employee_id = manager_id
start with manager_id is null;
