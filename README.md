# technician_project_php
Technician Project

Projects for
Murach’s PHP and MySQL
The projects in this document let you apply the programming skills you learn in Murach’s PHP and MySQL by developing an application called SportsPro Technical Support. This application is designed for the technical support department of a hypothetical software company that develops software for sports leagues, and it uses a database named tech_support.
The purpose of the application is to track technical support service calls (referred to as incidents) in a database that also stores information about the company’s customers, software products, and technicians. Before you do any of the projects, you should read the introductory information that follows.

An introduction to the projects	2
The design of the SportsPro Technical Support application	2
The design of the tech_support database	3
How to install the database	4
How to restore the database	4
How to structure your directories	4
How to format the web pages	4
A starting point for the projects	5
The projects	5
Project 6-1:	Manage products	6
Project 6-2:	Manage technicians	8
Project 6-3:	Manage customers	10
Project 6-4:	Register product	12
Project 6-5:	Create incident	14
Project 7-1:	Use a drop-down list	16
Project 8-1:	Improve controller code	17
Project 10-1:	Improve date handling	17
Project 12-1:	Use sessions	18
Project 14-1:	Use objects	19
Project 15-1:	Improve validation	20
Project 19-1:	Use prepared statements	21
Project 20-1:	Use the same form for adding and updating data	22
Project 20-2:	Assign incidents	24
Project 20-3:	Update incidents	27
Project 20-4:	Display incidents	30
Project 21-1:	Add user authentication	32

An introduction to the projects
This introduction describes the design of the SportsPro Technical Support application and the tech_support database. In addition, it explains how to make the tech_support database available to your applications, how to restore the database so it contains its original data, and how to prepare for developing the application. Finally, it provides some general information about developing the projects.
The design of the SportsPro Technical Support application
The SportsPro Technical Support application consists of web pages that provide functions for three types of users. First, it lets administrators perform functions such as maintaining the Products, Customers, and Technicians tables of the tech_support database. Second, it lets technicians perform functions such as updating incidents. And third, it lets customers perform functions such as registering products.
Most projects have you add one or more new pages to the SportsPro application. For example, project 6-1 has you add two pages that let an administrator manage the products in the database. If you complete all of the projects for this book, you’ll have a relatively realistic web application.
Note that the first number in a project refers to the chapter in the book. So, for example, you can complete projects 6-1 through 6-5 after reading chapter 6. Similarly, you can complete project 7-1 after reading chapter 7. However, some projects don’t require all of the preceding chapters. That’s why each project lists the required chapters.
The design of the tech_support database
The tech_support database is used to track technical support incidents. It consists of the seven tables shown in the diagram that follows. The incidents table contains one row for each technical support incident. Each row in the incidents table is related to one row in the customers table, which contains information about the company’s customers; one row in the products table, which contains information about the company’s products; and one row in the technicians table, which contains information about the company’s technical support staff.
In addition, a table named registrations keeps track of the products that are registered to each customer, a table named countries stores the countries of the world, and a table named administrators stores the usernames and passwords for the administrators. Note that the administrators table is not related to any of the other tables.

In addition to the column data types shown above, you should know that the customerID, incidentID, and techID columns in the customers, incidents, and technicians tables are AUTO_INCREMENT columns. So, the values of these columns are set automatically when new rows are added to these tables. For more details about this database, you can use phpMyAdmin to view the structure and data that’s stored in the database.
How to install the database
To install the tech_support database, you can start phpMyAdmin and run the tech_support.sql file that’s provided by your instructor.
How to restore the database
As you test some of the projects that you develop, you’ll need to add, modify, and delete rows in the database. Then, at some point, you may want to restore the original data. To do that, you can use phpMyAdmin to run the tech_support.sql file again. This deletes both the structure and the data of the current tech_support database and restores the original database.
How to structure your directories
As you develop the web pages needed for each project, you will need to decide where to store the files needed to implement each project. To keep each project independent of other projects, make sure to store each project in its own directory. For example, store the Manage Projects project in its own directory. This directory should have a descriptive name such as manage_projects or project_manager.
How to format the web pages
As you develop the web pages needed for each project, you will need to apply some formatting to them. To make that easier, you can use the main.css file that’s provided by your instructor. If necessary, you can modify this file, but it contains all of the tags needed to format the pages as shown in this document.
A starting point for the projects
To make it easy to get started, your instructor may give you the tech_support directory. This directory includes some of the files for a web site that can help you get started with the projects. These files include the tech_support.sql file that you can use to create the tech_support database, and a main.css file that you can use to format the web pages. If you run the web site, it displays a menu like the one shown here:

Most projects correspond to one of the links on this menu. However, at this point, if you click on any of these links, they display a message that indicates that the page is under construction. That’s because you still need to write the code that implements these projects.
The projects
The description of each project includes an image of how the pages should appear in a browser, a description of how the pages operate, and specifications for how the project should be coded. This information is detailed enough for you to complete each project. However, you’ll need to use your best judgment on how to code many of the details. To do that, write the code in the way that you think is best, based on the skills that were presented in the book.
Unless you’re instructed otherwise, you can implement each project using any programming techniques you wish. In some cases, however, the project’s specifications will direct you to use a specific programming technique. For example, a project may direct you to use sessions. In that case, you should implement the project as directed.
Project 6-1:	Manage products
For this project, you’ll create an application that lets an admin user view and delete existing products. In addition, this application lets the user add new products by entering the product information into text boxes. (Required reading: chapters 1-6)
The Product List page

Operation
When the user clicks the Delete button for a product, the product is deleted from the database.
When the user clicks the Add Product link, the Add Product page is displayed.
When the user clicks the Home link, the main menu is displayed.
The Add Product page

Operation
When the user enters the data for a new product into the text boxes and clicks the Add Product button, the product is added to the database and the Product List page is displayed again, so the user can view the newly added product.
When the user clicks the View Product List link, the Product List page is displayed.
Specifications
Validate the data the user enters on the Add Product page to be sure that the user enters a product code, name, version, and release date. If this data isn’t provided, display an Error page that indicates that a required field was not entered.
Project 6-2:	Manage technicians
For this project, you’ll create an application that lets an admin user view and delete existing technicians. In addition, this application lets the user add a new technician. (Required reading: chapters 1-6)
The Technician List page

Operation
When the user clicks the Delete button for a technician, the technician is deleted from the database.
When the user clicks the Add Technician link, the Add Technician page is displayed.
The Add Technician page

Operation
When the user enters the data for a new technician into the text boxes and clicks the Add Technician button, the technician is added to the database.
Specifications
Validate the data the user enters on the Add Technician page to be sure that the user enters data in every text box. If this data isn’t provided, display an Error page that indicates that a required field was not entered.
Project 6-3:	Manage customers
For this project, you’ll create an application that lets an admin user maintain customer data. To start, this application lets the user select an existing customer. Then, the user can view or update the customer’s data. (Required reading: chapters 1-6)
The Select Customer page

Operation
When the user enters a last name and clicks the Search button, the application displays a table of customers with the specified last name.
When the user clicks the Select button for a customer, the data for that customer is displayed on the View/Update Customer page.
The View/Update Customer page

Operation
When the user clicks the Update Customer button for a customer, the application updates the database. The user can also click the Back button or the Search Customers link to return to the Search Customers page without modifying the database.
Specifications
US is the country code for the United States. 
Project 6-4:	Register product
For this project, you’ll create an application that lets a customer register a product. (Required reading: chapters 1-6)
The Customer Login page

Operation
To log in, the customer can enter his or her email address and click on the Login button.
The Register Product page (view 1)

Operation
To register a product, the customer can select the product and click on the Register Product button.
Specifications
The Product drop-down list should include all products. If you have any trouble with this, look ahead to figure 7-5 in chapter 7 and figure 8-11 in chapter 8.
The Register Product page (view 2)

Operation
After the customer clicks on the Register Product button, the application displays a message that indicates that the product was registered successfully. This message should include the product’s code.
Project 6-5:	Create incident
For this project, you’ll create an application that lets an admin user enter new incidents. To do that, you’ll begin by letting the user select a customer. (Required reading: chapters 1-6).
The Get Customer page

Operation
To get a customer, the user can enter the customer’s email address. Then, the user can click on the Get Customer button to retrieve the customer’s data and display the Create Incident page.
The Create Incident page (view 1)

Operation
To create an incident, the user selects a product from the Product drop-down list, enters a title, enters a description, and clicks on the Create Incident button.
Specifications
The Product drop-down list should only include products that the customer has registered. If you have any trouble with this drop-down list, look ahead to figure 7-5 in chapter 7 and figure 8-11 in chapter 8.
The Create Incident page (view 2)

Specifications
If successful, the Create Incident page should display a message that indicates that the incident was added to the database.
Project 7-1:	Use a drop-down list
For this project, you’ll modify the Manager Customers application so it uses a drop-down list to display the country. Also, you’ll allow the user to use this drop-down to change the country. (Required reading: chapters 1-7).
The View/Update Customer page

Operation
When the user selects a customer, the View/Update Customer page should display the country in a drop-down list, and it should select the correct country for the customer. If you have any trouble with this, look ahead to figure 8-11 in chapter 8.
The user can use the Country drop-down list to change the country for the customer.
Specifications
In the Country drop-down list, display all countries that are available in the countries table in the tech_support database.
When the page is first displayed, make sure to select the correct country for the specified customer. To do that, write code that sets the selected attribute of the <option> tag for the appropriate country.
Project 8-1:	Improve controller code
For this project, modify one or more of the controller files so they use switch statements instead of if/else statements to select the appropriate action. (Required reading: chapters 1-6 and 8).
Project 10-1:	Improve date handling
For this project, you’ll modify the Manage Products application to improve its handling of the release date. (Required reading: chapters 1-6 and 10).
The Add Product page

Operation
The same as project 6-1, but the user can specify any valid date format for the release date.
Specifications
On the Product List page, use the mm-dd-yyyy format for the release date (no leading zeroes for the month or day). Also, don’t display any data for the time.
On the Add Product page, allow the user to use any standard date format.
Project 12-1:	Use sessions
For the Register Product application, let the customer skip the Customer Login page if he or she has already logged in. (Required reading: chapters 1-6 and 12).
The Register Product page

Operation
Same as project 6-4, but a customer who has logged in can skip the Customer Login page.
The customer can view the message on the Register Product page to verify that he or she is logged in.
To log out, the customer can click on the Logout button or close the browser. If the user clicks the Logout button, the Customer Login page is displayed.
Specifications
Use a per-session cookie for the session. That way, the session ends when the user closes the browser.
Store the customer data in the session. That way, you don’t have to use hidden fields to pass the customer ID to the controller.
Project 14-1:	Use objects
For the Manage Technicians application, use the object-oriented techniques described in chapter 14. (Required reading: chapters 1-6 and 14).
The Technician List page

Operation
Same as project 6-2. However, for the Technician List page, the First Name and Last Name columns are combined into a single Name column that contains the full name.
Specifications
Use a class named Database to get a connection to the database.
Store the Database class in a file named database_oo.php.
Use a class named Technician to store data about each technician. This class should include a method that returns the full name of the technician.
Store the Technician class in a file named technician.php.
Use a class named TechnicianDB to store the methods that access the data. These methods should accept or return a Technician object or an array of Technician objects whenever appropriate.
Store the TechnicianDB class in a file named technician_db_oo.php.
Project 15-1:	Improve validation
For the Manage Customers application, improve the data validation so it uses the techniques described in chapter 15. (Required reading: chapters 1-6, 14, and 15).
The View/Update Customer page

Operation
Same as 6-3, but with data validation for all fields on the View/Update Customer page.
Specifications
The first name, last name, address, city, state, and email are required and must have at least 1 and less than 51 characters.
The postal code is required and must have at least 1 and less than 21 characters.
You don’t need to validate the country field since the drop-down list requires the user to select a valid country.
The phone number must be in the (999) 999-9999 format.
The email address must be a valid email address.
The password must be at least 6 and less than 21 characters.
Project 19-1:	Use prepared statements
For all classes in the model, use the techniques described in chapter 19. This includes using prepared statements, returning arrays instead of PDOStatement objects, and using try/catch statements to handle data access errors. (Required reading: chapters 1-6 and 19)
The Database Error page

Operation
From the user’s point of view, all applications should work the same as they did previously. However, if any application encounters a database error, the user should see a Database Error page like the one above.
To simulate a database error, you can modify one of the SQL statements in the model so that it causes an error. For example, on the page above, the SQL statement is trying to access the “product” table instead of the “products” table.
Specifications
Modify all data access code so it uses prepared statements.
Modify all data access functions that return PDOStatement objects so they return arrays of rows instead.
Modify all data access functions so they use a try/catch statement to handle any data access errors that may occur. To do that, they can display a Database Error page like the one shown above.
Project 20-1:	Use the same form for adding and updating data
Enhance the Manage Customers application so it allows you to update the customer data in addition to being able to add and delete customer data. (Required reading: chapters 1-6 and 18-20)
The Customer Search page

Operation
Same as project 6-3, but the Add Customer button allows you to display the Add/Update Customer page.
The Add/Update Customer page

Operation
If the user is adding a new customer, this page should display blank fields and the Add Customer button as shown above.
If the user is viewing or updating an existing customer, this page should display the customer data and the Update Customer button as shown in project 6-3.
Project 20-2:	Assign incidents
For this project, you’ll create an application that assigns an incident to a technician. (Required reading: chapters 1-6, 12, and 18-20)
The Select Incident page

Operation
When this application starts, the Select Incident page uses a table to display all of the incidents that have not been assigned to a technician (techID IS NULL).
When the admin user clicks the Select button for an incident, the Select Technician page is displayed.
Specifications
Use a join in the SELECT statement for this page so it retrieves data from the incidents and customers tables.
Save the incident ID in the $_SESSION array so it can be used later in the application.
The Select Technician page

Operation
When the user clicks the Select button for a technician, the Assign Incident page is displayed.
Specifications
To get the number of open incidents for each technician, use a SELECT statement that includes a correlated subquery.
Save the technician ID in the $_SESSION array so it can be used later in the application.
The Assign Incident page (view 1)

Operation
When the user clicks the Assign Incident button, the selected incident is updated with the ID for the selected technician. If successful, this displays a message like the one shown below. Otherwise, an appropriate error message is displayed.
The Assign Incident page (view 2)

Operation
When the user clicks on the Select Another Incident link, the Select Incident page is displayed.
Project 20-3:	Update incidents
For this project, you’ll create an application that lets technicians update the rows in the incidents table. (Required reading: chapters 1-6, 10, 12, and 18-20)
The Technician Login page

Operation
After the technician logs in, the Select Incident page displays all incidents that have been assigned to the technician and have not been closed.
The Select Incident page

Operation
To select an incident, the technician can click on the Select button that corresponds to the incident. This displays the Update Incident page.
To log out, the user can click the Logout button.
If there are no open incidents for the current technician, this page does not display a table of incidents. Instead, it displays a message that indicates that there are no open incidents and a Refresh List of Incidents link. However, this link only displays new incidents if new incidents have been assigned to the technician.
The Update Incident page (view 1)

Operation
To update an incident, the technician can modify the description and optionally enter the date the incident was closed and click on the Update Incident button. If successful, this displays a message like the one shown below. Otherwise, an appropriate error message is displayed.
To log out, the user can click the Logout button.
The Update Incident page (view 2)

Operation
To view a list of the remaining open incidents, the technician can click on the Select Another Incident link. This skips the Technician Login page and goes directly to the Select Incident page.
If there are no open incidents for the current technician, this page does not display a table of incidents. Instead, it displays a message that indicates that there are no open incidents and a Refresh List of Incidents link. However, this link only displays new incidents if new incidents have been assigned to the technician.
Project 20-4:	Display incidents
For this project, you’ll create an application that displays all the assigned and unassigned incidents. (Required reading: chapters 1-6, 10, and 18-20)
The Unassigned Incidents page

Operation
When the application starts, it displays information about all incidents that have not yet been assigned to a technician.
To display the incidents that have already been assigned to a technician, the admin user can click on the View Assigned Incidents link.
Specifications
Display the customer name, the product name, and the four required columns of incident data (incident ID, date opened, title, and description).
The Assigned Incidents page

Operation
To display the incidents that haven’t been assigned, the admin user can click on the View Unassigned Incidents link.
Specifications
Display the same data as the Unassigned Incidents page plus the technician’s name and the date the incident was closed. If the incident hasn’t been closed, display “OPEN” instead of the date.
Project 21-1:	Add user authentication
For this project, you will use a secure connection and require all users to log in including customers, technicians, and administrators. (Required reading: chapters 1-6, 10, and 21)
The Home page

Operation
If you’ve been using the starting Home page for these projects, you’ll have to replace it with a Home page like the one above.
When the user clicks one of the links on the main menu, the application displays a login form that’s appropriate for the type of user.
The Admin Login page

Operation
When the user enters a valid username and password, the Admin Menu page is displayed. Otherwise, the Admin Login page is displayed again.
To log in, you can use “admin” as the username and “sesame” as the password.
The Admin Menu page

Operation
To navigate to an application, the user can click on the appropriate link.
The page displays a message that indicates the login status.
To log out, the user can click on the Logout button. This displays the Main Menu page.
Specifications
All pages should include a link to the Home page in the header for the page.
Except for the Home page, all pages should use a secure (https) connection.
No pages should allow an unauthorized user to access them. For example, only a user that’s logged in as an administrator should be able to access the Admin Menu page.
The Technician Login page

Operation
When the user enters a valid technician email and password, the Select Incident page is displayed. Otherwise, the Technician Login page is displayed again.
The Select Incident page

Operation
Same as project 20-3, but the bottom of the page displays a message about the technician that’s logged in and provides a Logout button that the technician can use to log out.
If there are open incidents for the current technician, this page displays a table of incidents as shown in project 20-3.
If there are no open incidents for the current technician, this page displays a message and a link as shown above. However, this link only displays new incidents if new incidents have been assigned to the technician.
The Customer Login page

Operation
When the user enters a valid customer email and password, the Register Product page is displayed. Otherwise, the Customer Login page is displayed again.
The Register Product page

Operation
Same as project 6-4, but the bottom of the page displays a message about the customer that’s logged in and provides a Logout button that the customer can use to log out.
