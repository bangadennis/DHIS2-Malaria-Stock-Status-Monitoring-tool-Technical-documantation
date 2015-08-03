Development tools
===================
Below is a description of the development tools and technologies used to develope the malaria stock status monitoring tool.

Database - MySQL
------------------
- A MySQL database is used to store data.

- However, another database like PostgreSQL can also be used.

- The choice of the database was purely due to:

	 - The rapid turn around time.
	 - It manages memory very well: MySQL server has been thoroughly tested to prevent memory leaks.
	 - It runs on many operating systems: MySQL runs on many operating systems, including Novell NetWare, Windows,Linux, many varieties of UNIX* (such as Sun* Solaris*, AIX, and DEC* UNIX), OS/2, FreeBSD*, and others.
	 - It supports several development interfaces: Development interfaces include JDBC, ODBC, and scripting (PHP and Perl), letting you create database solutions that run not only in your NetWare 6.5 environment, but across all major platforms, including Linux, UNIX, and Windows.

PHP and Apache2 for the server side
-------------------------------------
- The scripting language PHP and web server Apache2 were used for the server side logic.

- **CodeIgniter** PHP framework was used to develop the system.

JavaScript
------------
JavaScript was used in the client side for validation and for responsives purposes.



HTML5, Bootstrap and JavaScript for user interface
----------------------------------------------------
Since this is a Web application, the interface is coded in HTML5 with Bootstrap framework incorporated to provide a better user experience JavaScript is also used to make the interface responsive and event/data driven.



.. toctree::
    :maxdepth: 2
