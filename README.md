AUTOGEAR INTEGRATED GARAGE & INVENTORY MANAGEMENT SYSTEM 

ABSTRACT 
This report presents the development of "AutoGear", a web-based smart Integrated 
Garage and Inventory Management System designed to resolve operational 
inefficiencies at Sunrise Auto Spa Grand in Kundasale, Kandy. Currently, the client 
relies entirely on manual ledger systems, leading to persistent challenges such as 
calculation errors, a critical lack of synchronization between sales and stock thresholds, 
difficulty tracking customer debts, and missed vehicle service follow-ups.  
To address these limitations, the "AutoGear" application was developed using the PHP 
Laravel framework, integrated with a MySQL database, and designed with a mobile
responsive interface using HTML, CSS, and JavaScript. The system's functional 
architecture incorporates structured authentication, dynamic stock control with 
predictive safety thresholds, digital job cards, automated profit/loss calculation, and a 
smart reminder engine connected to a WhatsApp communication workflow.  
System evaluation, comprised of functional testing and a user experience 
survey, demonstrated high computational accuracy for decimal invoice computations 
and seamless database synchronization. By replacing manual paperwork with digital 
automation, the final web application successfully provides high administrative 
transparency, minimizes stock shortages, and improves customer retention through 
proactive outreach.  

Scope of the Project 
The system scope is defined by five modules: User Authentication (with separate 
dashboards for Admin and Technicians), Smart Inventory Management, Service 
Tracker and Digital Job Cards, Automated Overdue Reminders, and Profit/Loss 
Analytic

Selection of the Development Framework 
The "AutoGear" system is developed using the Laravel framework, a robust and modern 
PHP web application framework. Selecting Laravel over raw PHP or alternative server
side frameworks provides several technical and structural advantages crucial for this 
project:  
• Eloquent ORM: Laravel features a powerful built-in Object-Relational Mapping 
(ORM) layer. This allows the database tables (such as customers, job cards, inventory 
parts, and billing logs) to be represented as PHP classes and queried using intuitive, 
expressive syntax instead of executing raw SQL commands. This simplifies data 
manipulation and relationship handling between complex business modules.  
• Built-in Routing and Blade Engine: The framework provides a clean, secure routing 
system and utilizes the Blade templating engine. Blade allows for modular, reusable 
layout designs which are essential when building responsive dashboards for garage 
technicians and administrators.  
6 
• Security and Access Control: Laravel includes pre-configured authentication 
controls, route protection, and security features like CSRF protection. These features 
facilitate the seamless integration of role-based access control (RBAC), dividing 
permissions securely between the Garage Owner (Admin) and Workshop Technicians.  
• Database Migrations: The migration system serves as a version-control tool for the 
database schema, enabling iterative structural updates without risking data loss during 
the rapid prototype phases of the development cycle.  

Database Technology 
MySQL was selected as the relational database engine for the "AutoGear" system, 
managed via a MariaDB server during local development. A relational database system 
is highly suited for this application because the underlying data is naturally structured 
and relational:  
• Every Customer profile is linked to specific Vehicles. 
• Every Job Card connects to a unique vehicle, customer, and the technician assigned.  
• Every bill or invoice item references a unique Spare Part from the inventory and a 
specific Job Card.  
By utilizing MySQL, foreign key constraints are enforced directly at the database level 
to maintain strict referential integrity. Features such as cascading deletes ensure that if 
a transaction record or job card is removed, orphaned billing line items do not corrupt 
or clutter the storage. High-precision decimal support is also native to MySQL, 
fulfilling the implementation requirement for precise spare-part weighing and labor cost 
calculations.  

Architectural Pattern 
The system is built upon the Model-View-Controller (MVC) architectural pattern, 
which is natively supported and enforced by the Laravel framework. This pattern strictly 
segregates the system concerns into three isolated tiers:  
1. Model: Manages the data representation, relational constraints, and database 
communication (e.g., JobCard, SparePart, Customer, and Payment models).  
7 
2. View: Handles the user-interface presentation layer rendered using HTML, CSS, and 
dynamic JavaScript.  
3. Controller: Acts as the intermediary logic center. It intercepts HTTP requests from 
the garage operator, processes input data (e.g., checking stock levels before approving 
a job card), and updates the models or views accordingly.  
This structural separation increases code maintainability, allowing backend business 
workflows (like the smart reminder logic) to be updated independently without 
affecting the user interface.  

Development Environment 
The software development environment utilizes the following tools to manage, write, 
and version-control the application:  
• Visual Studio Code: Serving as the primary lightweight source code editor for 
development across PHP, HTML, CSS, JavaScript, and Blade layouts.  
• XAMPP: Used to simulate a local host environment on the development PC. It 
bundles the Apache web server, PHP execution environment, and MariaDB server for 
seamless local testing.  
• Git: Employed for local and remote version control. It tracks progressive script 
changes and facilitates safe rollbacks when testing new algorithms. 
