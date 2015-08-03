Deployment of the system
===========================

These instructions show you how to install the malaria stock status monitoring system on any web server. Please check out  operating systems specific guides for Linux server, Windows Server and Mac OSX.

Installation Steps 
-------------------
step 1
~~~~~~~~
- Make sure the webserver has MySQL and PHP support.

.. note::

        e.g in Windows server,
        Step 1: **Download the installation files**. You will need to download and install the windows version of the installers for each of the below componments:

            #. Apache. Apache is the HTTP (Web) server software.
            #. PHP. PHP is the general-purpose scripting language, especially suited for Web development, that will be used.
            #. MySQL Server. MySQL is the database server/software will be used.

        Step2:**Install Apache**. Run the Apache install file. You will need to follow the prompts and respond accordingly. When you reach the window that asks for server information, you may enter the following:
            #. Network Domain: localhost
            #. Server Name: localhost
            #. Administrator Email: (any email address).
            
        Step 3: **Install PHP**. Run the PHP installation file which you downloaded in Step 1. 

        Step 4: **Install MySQL**. Run the MySQL installation file which you downloaded in Step 1. 
                - Select the option for the "Typical" isntallation.
                - You will then click on "Install". 


Step 2
~~~~~~~
- Put the project into the webroot of the server. For Ubuntu servers, the webroot is in *var/www/html* while in Windows server, its located in xampp(WAMP)/htdocs.


Step 3
~~~~~~~~~~
Configure the database settings to fit the application that is to be deployed. Visit the domain or IP address in your web browser. After a couple of minutes, the web application will be set up.

Deployment on Linux (Unix) servers
--------------------------------------

It is important to ensure you check the Server Requirements list before deploying on your unix server.

At a high level you will need a:

    - Web server ie Apache
    - Database ie MySQL
    - PHP

  You should have a working LAMP (Linux + Apache  + MySQL + PHP) installation before the actual deployment of the system.

  .. note::

    The user has to be root when installing applications by typing *sudo su* on the terminal.

For Ubuntu servers, visit `this page for LAMP installation`_.

.. _`this page for LAMP installation`: http://howtoubuntu.org/how-to-install-lamp-on-ubuntu

Deploying the system on Ubuntu server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    - Once all of the above requirements are installed, the application folder is uploaded into the web directory. 
    - Upload the database file into the phpMyadmin of the web server.
    - Configure the databse for use by the application.
    - The application can now be accessed throught the browser using the IP address or the defined url.


Windows server with WAMPServer 2.5+
------------------------------------
Installing  WAMP
~~~~~~~~~~~~~~~~~
    #. Go to the `WampServer download page`_.
    #. You will first need to download and install the suggested `Visual C plus plus Redistributable for Visual Studio 2012 Update 4`_ BEFORE installing WampServer.
    #. Next, download the WampServer installer and the run the installer. By default, it will install to C:\wamp. You can choose your own install path if you wish; however note we will refer to the c:/wamp in the test of this tutorial.
    #. Once WampServer has been installed and launched, you will see a small "W" in the task bar, next to the clock. If everything is working, then it will be green. If it's orange or red, then something is likely misconfigured. See the Troubleshooting section below. If you can't see the "W", then WampServer hasn't been started and you should start WampServer from the start menu.
    #. Left-click the "W", then select Apache -> Apache Modules -> Rewrite Module. The "W" will flick to orange, and then return to green.
    #. Left-click the "W", then select MySQL -> my.ini. At the very bottom of the file, and add the following to a new line without the quotes): "lower_case_table_names = 2". Save the file, close #. Notepad and left-click the "W", and select 'Restart all services'. This is used to ease the transition between a Windows-based install and a Linux-based install where database case-sensitivity is important.



.. _`Visual C plus plus Redistributable for Visual Studio 2012 Update 4`: http://www.microsoft.com/en-us/download/details.aspx?id=30679#


.. _`WampServer download page`: http://www.wampserver.com/en/#download-wrapper



.. toctree::
    :maxdepth: 2
