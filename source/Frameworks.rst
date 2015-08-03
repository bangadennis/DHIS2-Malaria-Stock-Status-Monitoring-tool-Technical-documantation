Frameworks
===========
The system is built using **Codeigniter**, a php framework.

CodeIgniter is an Application Development Framework - a toolkit - for people who build web sites using PHP. Its goal is to enable you to develop projects much faster than you could if you were writing code from scratch, by providing a rich set of libraries for commonly needed tasks, as well as a simple interface and logical structure to access these libraries. CodeIgniter lets you creatively focus on your project by minimizing the amount of code needed for a given task.

Source Code Structure
----------------------
The source code is organized into **Model-View-Controller** development pattern. This is because CodeIgniter is based on the Model-View-Controller development pattern. MVC is a software approach that separates application logic from presentation. In practice, it permits the web pages to contain minimal scripting since the presentation is separate from the PHP scripting.

    - The **Model** represents your data structures. Typically your model classes will contain functions that help you retrieve, insert, and update information in your database.

    - The **View** is the information that is being presented to a user. A View will normally be a web page, but in CodeIgniter, a view can also be a page fragment like a header or footer. It can also be an RSS page, or any other type of “page”.

    - The **Controller** serves as an intermediary between the Model, the View, and any other resources needed to process the HTTP request and generate a web page.

CodeIgniter has a fairly loose approach to MVC since Models are not required. 

CodeIgniter framework was chosen for:
	 - maximum performance
	 - capability, and 
	 - flexibility in the smallest, lightest possible package.