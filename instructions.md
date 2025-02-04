# Instructions  

- Use Ctrl + / to toggle commenting

## The objective of this homework assignment is
- to write the contents of the file (employees.txt) to a list
- we will lookup employee from this list
- we will update employee name in this list
- we will delete employee from this list
- we will display employees from this list
- after all these operations are done, we will write this list back to the file

🚩 Note: Changes will not reflect in the file immediately. You will see the changes in the list.

<details>
  <summary>
    ✅ Copy code from CW03
  </summary>

  - Copy main.py, validations.py and functions.py
  - We won't be using functions.py, but it will be nice to have it if you need parts of the code
  - In main.py, move the function call to main inside the if block <code>if \_\_name\_\_ == "\_\_main\_\_":</code>
</details>

<details>
  <summary>
    ✅ Add a new file
  </summary>
  
  - Create a new file named list_functions.py and to this file
  - Copy all the functions from functions.py (we will modify these functions to perform list operations)
  
</details>

<details>
  <summary>
    ✅ Download a file
  </summary>
  Download this file https://github.com/suchialex/pretty-print/blob/main/suchi_pretty_print.py to your project folder
</details>

## In list_functions.py

<details>
  <summary>
    ✅ Define function file_to_list
  </summary>
  Objective: This function will read the contents of the employees.txt file line by line and store in a list. This list is returned to the calling function.

  - This function does not accept any parameters

In the function body,
  - First, 
  - In try block, open the file employees.txt in read mode and store it in a file pointer
  - In the except block
  -   Write a statement to print `File Not Found`
  -   return an empty list
  - In the else block,
    - Create an empty list (this list will contain all the employees data)
    - Using the above file pointer, start a for loop with a loop variable of your choice (this variable will read each line of the file)
      - Strip off the newline character from the loop variable
      - Now append it to the empty list you created above
    - Outside the for loop close the file
    - Return the list
    - 💡If you are familiar with list comprehension, you may use that to create the list from file
</details>


<details>
  <summary>
    ✅ Inside employee_operations(), call the function file_to_list()
  </summary>

   - After the print("Employee Management") statement in employee_operations() function,
   - Call the function file_to_list()
   - Store the returned list in a variable
   - Print the list (you may use suchi_print(), after importing it using `from suchi_pretty_print import suchi_print`)
   - Execute the code to see if your employees data is being printed correctly
   - If everything is executing correctly, you may comment out the print statment now
</details>


<details>
  <summary>
    ✅ Modify lookup_employee()
  </summary>

  This function NOW takes two parameters 
  - the employees list 
  - the employee_id we are trying to lookup 

  It returns two values 
  - found (boolean) - True if the employee is found, False if not
  - index (the integer position in the list where the employee_id was found, we don't find the employee, we will return 0)

In the function body
  - Clear the existing code
  - Using an if statement and the in operator, check if the employee_id (passed as parameter) is present in the employees list (passed as parameter)
  - If yes,
    - Get the index of the employee id in the list
    - Using this index, print the Name, Department and Salary
    - return True and the index obtained above
  - If not
    - print `Employee Not Found`
    - return False and 0
</details>


<details>
  <summary>
    ✅ Modify the lookup_employee() function call
  </summary>

  - Inside employee_operations() in the appropriate elif block,
  - Modify the lookup_employee() call - we are now passing TWO arguments, the list obtained earlier and the employee id from the above step, in that order
  - Store the returned values in TWO variables - choose names for these variables
  - You may delete the if block and the print `Employee Not Found` statement (we are doing this inside the lookup function)
  - 📜Test your code by entering an employee ID that exists and an employee ID that doesn't exist
</details>


<details>
  <summary>
    ✅ Define display_employees()
  </summary>
  The objective of this function is to display all employees in a tabular format
  
  - This function takes one parameter - the employee list<br>
  - This function returns nothing, so it is a void function<br>

  In the function body

  - Get the employee id slice, employee ids start at the beginning of the list and appear at every fourth item in the list
  - Use a for loop to go over the id slice obtained above, name your loop variable whatever you want (this variable will have the employee id one at a time)
  - Inside the for loop find the index of the loop variable in the employees list and store in a variable named position
  - Using a print statement, print the ID (employees[position]), name (employees[position+1], etc.) in a tabular format
</details>



<details>
  <summary>
    ✅ Modify display_employees() function call
  </summary>
  
  - In the appropriate elif block, modify the display_employees() call - now we are passing one argument - the employees list (obtained from the file_to_list function)
</details>


<details>
  <summary>
    ✅ Define update_employee_name()
  </summary>
  The objective is to get an employee ID and call the lookup_function to see if that employee exists in the list, if yes, we use the index returned by the lookup function and update the name which will be at index+1 position. This function takes the employee list as parameter and returns the modified employee list back<br>

  
In the function body

  - Clear the existing code (you may leave the print statement)
  - Ask the user to provide the employee ID whose name needs to be updated and store in a variable
  - call the lookup function using the employee list passed as the parameter and the above variable
  - store the returned values in two variables
  - check if the first variable is True, if yes
    - Ask the user to provide a new first name by calling the validate_first_name() function
    - Ask the user to provide a new last name by calling the validate_last_name() function
    - 🚩 You may have to import the validations module
    - concatenate the first and last names with a space in between 
    - then modify the index+1 position in the employees list with the new full name
  - Outside the if block, return the employees list
</details>

<details>
  <summary>
    ✅ Modify the update_employee_name() call
  </summary>
  In the appropriate elif block modify the update_employee_name - it now accepts one argument, employees list returned by file_to_list. Store the returned list in the same employees list variable (for simplicity)
</details>


<details>
  <summary>
    ✅ Modify delete_employee() function
  </summary>
  The objective is to ask the employee to enter the employee ID to be deleted and delete the corresponding elements from the employees list

  - This function accepts one parameter - the employee list
  - It returns one parameter - the modified employee list

  In the function body<br>

  - Ask the user for the employee ID to be deleted and store in a variable
  - Call the lookup function using the employees list passed as the parameter and the employee ID above
  - Store the returned values in two variables
  - If the first returned variable is True,
    - Write a statement to delete the element in the employees list at index position returned as the second value by the lookup function
    - Write the same statement three more times to delete the rest of the employee data elements from the list
  - Outside the if block, return the employees list
</details>


<details>
  <summary>
    ✅ Modify the delete_employee() function call
  </summary>
  In the apprpriate elif block, modify the delete_employee() function - it now takes one argument, the employees list. Store the returned list in the same variable (for simplicity)

</details>


<details>
  <summary>
    ✅ Define list_to_file()
  </summary>
  The objective is to write all the list elements back to the file<br>

  - This function accepts one parameter, the employee list
  - This function returns nothing, so it is a void function

    In the function body<br>

  - Open the file employees.txt in write mode (not append mode) and get the file object/pointer
  - Use a for loop to go over the list elements, this list is the parameter passed to this function
  - To each list element, append a newline character and write it to the file using the file pointer obtained above
  - Outside the for loop, close the file

</details>


<details>
  <summary>
    ✅ Call the list_to_file() function
  </summary>
  In employee_operations() function, outside the while loop<br>
  Call the function list_to_file passing the employee list as argument
</details>
