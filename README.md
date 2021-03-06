# Address Management System

 Many services you use require address information for the user and store such information. This address changing system allows users to register and manage their addresses in one place. While the other service providers retrieve the users address from this system. 


# Software Function

Our software application is an address management system that allows users to upload their contact details  whilst keeping track of their accounts and also allows companies (service providers) to retrieve contact details of individuals registered on the system. For the implementation, we adopted a  model-view-controller architecture in our system. The purpose of this was to separate our system logic to three layers which are connected: model, view and controller. Our users use the controller to make a change in the model which updates their view.

Our system makes use of two controllers, “addresscontroller.php” and “logincontroller.php” files which extends their base classes, “addressclass.php”  and “loginclass.php” files respectively. These base classes hold methods that are relevant to them. Functions performed by regular users, such as add and update address in the “addresscontroller.php” file are called in the model “addressproc.php” file. The search function performed by service providers in the “addresscontroller.php” file is called in the model “spaddressproc.php” file. Functions to handle the login and signup capabilities of our users are found in the “logincontroller.php” file. This file is connected and called by two other model files “loginproc.php” and “registerproc.php”. All these model files are connected to their respective view files which they will be updating, namely, “addaddress.php”, “spsearchaddress.php”, and “updateaddress.php” for address manipulation; and “index.php” and “register.php” for logging in and registering to the system. This views allows the model to be displayed to the user and sends action made by the user to the controller.

For users to use the application, they first have to register onto the platform if they do not have accounts after which they log onto the system. When they are successfully logged onto the system, they can add their contact (address) details as well update their contact details. For service providers, they also have to register if they do not have accounts and login afterwards. After successfully logging onto the system, there is a search bar which allows them to search for the contact details of any registered individual using unique address identifiers.


# Data Structure

A hash table is a data structure that enables data storage in an associative approach. Here, the data is kept in as an array with a unique index value assigned to this data. This allows for swift access of data given its index.
The hash table is implemented in our system with the “password_hash()” function, a built-in PHP function to store user’s passwords securely. A one-way operation which generates a model of a password is called a hash. During the registration process, our system accepts a password from our user and using this algorithm, it hashes this password which is sent to our database. During the logging process, the user enters their email and password. This password inputted by the user is hashed once more and cross checked with what is stored in the database. The user will be directed to his relevant interface if both hashes are a match. 

“Password_hash()” is implemented in our system to avoid the user’s passwords to be saved in our database as plain text as this becomes a security flaw when the password can be read by anyone. Hashing passwords makes it almost impossible for intruders to interpret thus preventing unauthorized access to our system. We found it necessary to use this data structure because it gave us the opportunity of saving user passwords swiftly in a secure manner. This implementation was done in our login class found in the “loginclass.php” file.


# Technology & Justification

The main technologies we employed in this application are html, css, javascript, php and mysql because our application is a web application therefore these technologies are essential.

Personal Home Page (PHP) Tools is a server-side programming language used here to make dynamic web pages that would interact with our database. PHP allowed users to transfer data to and from the database depending on which function they execute. For example, when a regular user is filling out his address details on a form, PHP allows his/her details to be sent to the database for storage and retrieval by the service provider. 

HyperText Markup Language (HTML) is a markup language and an essential tool used for building up the website. Here, HTML was utilized in giving the description of how information is organized on our web pages. HTML codes were written inside of our PHP files.

JavaScript (JS) is a client-side programming language used for scripting to make websites dynamic. This language is executed by the user’s web browser instead of on the web server. For this project, JavaScript was used to validate the form inputs entered by our users (Regular Users and Service Providers). Form fields are set to accept only to accept a particular group of elements and strict validation rules are used. If a field is found to have invalid data, the user is prompted to make modifications. Using JavaScript for form validation is essential as it prevents users from entering legitimate data that could pose security risks to our system.

Cascading Style Sheets (CSS) is a programming language used here to design how the web pages should be displayed. This design includes colours, font and the overall layout.This makes our system more user-friendly and inviting to our users as CSS gives style to our web pages. To reduce the total number of files, our CSS was embedded into our PHP file.
The more commonly known CSS and JS framework, Bootstrap 4 was used in our system. This framework holds CSS and JS model templates for forms, navigations, buttons, fonts and further interface elements. Using Bootstrap allowed us to design our website much faster and simpler as ready-made templates interface components were available.

My Structured Query Language (MYSQL) is a relational database management system used here to develop a database for storing and handling data. Tables, namely “ulogin” and “address”  were defined in our database to hold relevant data. The “ulogin” table holds registration and login information for each user to be stored after a successful registration and retrieved when the user wants to login. The “address” table holds address details of our registered regular user, namely building number, street name, city, state, country, and zip code. This table is useful to collect and store such information about regular users along with its retrieval by service providers.
