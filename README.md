Download Link: https://assignmentchef.com/product/solved-dbs211-assignment-1
<br>
In this assignment, you create a simple HR application using the C++ programming language and Oracle server. This assignment helps students learn a basic understanding of application development using C++ programming and an Oracle database.

<strong>Instruction:</strong>

In this assignment, we use the same database that you use for your labs.

<strong><em>Connecting to an Oracle database from a C++ Program</em></strong>




In your function <strong><em>main()</em></strong>, create a connection to your database.




You need to implement the following functions:

<strong><em>int menu(void);</em></strong>




The <strong><em>menu()</em></strong> function returns an integer value which is the selected option by the user from the menu. This function displays the following menu options:




<ul>

 <li>Find Employee</li>

 <li>Employees Report</li>

 <li>Add Employee</li>

 <li>Update Employee</li>

 <li>Remove Employee</li>

 <li>Exit</li>

</ul>




Before printing the menu, display the following title on the screen




********************* HR Menu *********************




Prompt the user to enter an option. If the user enters an incorrect option, the user is asked to enter an option again. When the user enters a correct option (0 to 5), the function returns the selected value.




If the user selects 0 (Exit), the program terminates.




<strong><em>int findEmployee(*conn,  int employeeNumber, struct Employee *emp);</em></strong>




This function receives a connection object, an integer number as the employee number, and a pointer to a variable of type Employee. The function returns 0 if the employee does not exist. It returns 1 if the employee exits.

To store the employee data from the <strong><em>findEmployee()</em></strong> function, we use a variable of type structure called Employee. The Employee structure has the following members:




<strong>struct Employee{</strong>

<strong>int employeeNumber;</strong>

<strong>char lastName[50]; </strong>

<strong>char firstName[50]; </strong>

<strong>char email[100];  </strong>

<strong>char phone[50]; </strong>

<strong>char extension[10]; </strong>

<strong>char reportsTo[100];  </strong>

<strong>char jobTitle[50]; </strong>

<strong>char city[50]; </strong>

<strong> </strong>

<strong>};</strong>

The <em>ReportsTo</em> member stores the first name and the last name of the employee who is the manager of the given employee number.

If the employee exists, store the employee data into the members of an Employee variable using the third parameter in the <strong><em>findEmployee()</em></strong> function which references to that variable of type Employee.




<strong><u>Note</u></strong>: For this report, you may need to query more than one table (join).













<strong> </strong>

<strong><em>void displayEmployee(*conn, struct Employee emp);</em></strong>




If the user selects option 1, this function is called. First, prompt the user to enter a value for the employee number. Then, call function <strong><em>findEmployee()</em></strong> to check if the employee with the given employee number exists. If the returning value of function <strong><em>findEmployee()</em></strong> is 0, display a proper error message.

Sample error message:




Employee 1122 does not exist.




Otherwise, call the function <strong><em>displayEmployee() </em></strong>to display the employee information.

This function receives a connection pointer and values of a variable of type Employee and displays all members of the emp parameter.




Display the employee information as follows:




employeeNumber = 1002

lastName = Murphy

firstName = Diane

email = <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="94f0f9e1e6e4fcedd4f7f8f5e7e7fdf7f9fbf0f1f8f7f5e6e7baf7fbf9">[email protected]</a>

phone = +1 650 219 4782

extension = x5800

reportsTo =

jobTitle = President

city = San Francisco







<strong><em>void displayAllEmployees(*conn);</em></strong>

If the user selects option 2 (Employees Report), call function <strong><em>displayAllEmployees().</em></strong>

This function receives a connection pointer and displays all employees’ information if exists.










Write a query to select and display the following attributes for all employees.




E          Employee Name         Email                                       Phone              Ext            Manager————————————————————————————————————————

1002           Diane Murphy                                  <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a3c7ced6d1d3cbdae3c0cfc2d0d0cac0ceccc7c6cfc0c2d1d08dc0ccce">[email protected]</a>                     +1 650 219 4782          x5800

1056           Mary Patterson                                <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="c3aeb3a2b7b7a6b1b0ac83a0afa2b0b0aaa0aeaca7a6afa0a2b1b0eda0acae">[email protected]</a>                   +1 650 219 4782          x4611         Diane Murphy

1076           Jeff Firrelli                                         <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="ee8488879c9c8b828287ae8d828f9d9d878d83818a8b828d8f9c9dc08d8183">[email protected]</a>                         +1 650 219 4782          x9273         Diane Murphy

1143           Anthony Bow                                    <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="1d7c7f726a5d7e717c6e6e747e70727978717e7c6f6e337e7270">[email protected]</a>                            +1 650 219 4782          x5428         Mary Patterson

1165           Leslie Jennings                                  <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="7a16101f141413141d093a19161b0909131917151e1f16191b080954191517">[email protected]</a>                     +1 650 219 4782          x3291                    Anthony Bow

1166           Leslie Thompson                              <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="4529312d2a2835362a2b0526292436362c26282a212029262437366b262a28">[email protected]</a>                  +1 650 219 4782          x4065                    Anthony Bow

1188           Julie Firrelli                                       <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b8d2ded1cacaddd4d4d1f8dbd4d9cbcbd1dbd5d7dcddd4dbd9cacb96dbd7d5">[email protected]</a>                         +1 215 837 0825          x2173                    Anthony Bow

1216           Steve Patterson                                <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="97e4e7f6e3e3f2e5e4f8f9d7f4fbf6e4e4fef4faf8f3f2fbf4f6e5e4b9f4f8fa">[email protected]</a>                  +1 215 837 0825          x4334                    Anthony Bow

1286           Foon Yue Tseng                                <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="91f7e5e2f4fff6d1f2fdf0e2e2f8f2fcfef5f4fdf2f0e3e2bff2fefc">[email protected]</a>                          +1 212 555 3000          x2248                    Anthony Bow

1323           George Vanauf                                 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="7f18091e111e0a193f1c131e0c0c161c12101b1a131c1e0d0c511c1012">[email protected]</a>                       +1 212 555 3000          x4102                    Anthony Bow

1102           Gerard Bondur                                 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="4324212c2d27363103202f2230302a202e2c27262f202231306d202c2e">[email protected]</a>                      +33 14 723 4404          x5408         Mary Patterson

1337           Loui Bondur                                      <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="fb979994959f8e89bb98979a8888929896949f9e97989a8988d5989496">[email protected]</a>                       +33 14 723 4404          x6493                    Gerard Bondur

1370           Gerard Hernandez                           <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="91f6f9f4e3fff0fff5f4d1f2fdf0e2e2f8f2fcfef5f4fdf2f0e3e2bff2fefc">[email protected]</a>                  +33 14 723 4404          x2028                    Gerard Bondur

1401           Pamela Castillo                                 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b4c4d7d5c7c0ddd8d8dbf4d7d8d5c7c7ddd7d9dbd0d1d8d7d5c6c79ad7dbd9">[email protected]</a>                       +33 14 723 4404          x2759                    Gerard Bondur

1702           Martin Gerard                                  <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="076a60627566756347646b6674746e646a6863626b646675742964686a">[email protected]</a>                      +33 14 723 4404          x2312                    Gerard Bondur

1621           Mami Nishi                                        <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="9ff2f1f6ecf7f6dffcf3feececf6fcf2f0fbfaf3fcfeedecb1fcf0f2">[email protected]</a>                          +81 33 224 5000          x101           Mary Patterson

1625           Yoshimi Kato                                     <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="2e57454f5a416e4d424f5d5d474d43414a4b424d4f5c5d004d4143">[email protected]</a>                            +81 33 224 5000          x102           Mami Nishi

1088           William Patterson                            <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="0275726376766770716d6c42616e6371716b616f6d66676e616370712c616d6f">[email protected]</a>                 +61 2 9264 2451          x4871         Mary Patterson

1611           Andy Fixter                                       <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="96f7f0ffeee2f3e4d6f5faf7e5e5fff5fbf9f2f3faf5f7e4e5b8f5f9fb">[email protected]</a>                          +61 2 9264 2451          x101                    William Patterson

1612           Peter Marsh                                      <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="9feff2feedecf7dffcf3feececf6fcf2f0fbfaf3fcfeedecb1fcf0f2">[email protected]</a>                        +61 2 9264 2451          x102                    William Patterson

1619           Tom King                                           <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="27534c4e494067444b4654544e444a4843424b444655540944484a">[email protected]</a>                             +61 2 9264 2451          x103                    William Patterson

1501           Larry Bott                                           <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6c000e0318182c0f000d1f1f050f01030809000f0d1e1f420f0301">[email protected]</a>                             +44 20 7877 2041       x2311                    Gerard Bondur

1504           Barry Jones                                       <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="1d7f777273786e5d7e717c6e6e747e70727978717e7c6f6e337e7270">[email protected]</a>                         +44 20 7877 2041       x102                    Gerard Bondur




<strong><u>Note</u></strong>: For this report, you may need to query more than one table (join).

If the query does not return any rows, display a proper message:

There is no employees’ information to be displayed.

<strong><u>Note</u></strong>: For each query in your assignment, make sure you handle the errors and display the proper message including the error_code.

Error_code is a number returned if the query execution is not successful.