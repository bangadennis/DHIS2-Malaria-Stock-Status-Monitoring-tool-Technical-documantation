The Database Schema
=====================

Introduction
--------------
This documentation set describes the data characteristics of the tables and columns in the malaria stock status monitoring  database: including datatypes and sizes, nullability, index, sequence, key and constraint information. Additional commentary is also provided for key tables and columns.

Here is the screenshot of the database schema:

    .. figure:: images/DatabaseSchema.png



		


Database  Tables
-----------------------
		#. User_table
		#. County_level_soh
		#. Commodity_forecast_data
		#. Current_stock
		#. Pending_shipment_details
		#. Counties
		#. Central_level_data
		#. Facility_level_data
		#. County_level_reporting_rates
		#. Zones
		#. Supply_chain_agencies
		#. County_level_data
		#. Mapping_drugs_category
		#. Facility _level_reporting_rates
		#. Funding_agencies
		#. Facility_level_soh
		#. Malaria_commodities
		#. Planned_procurement_details


Tables attributes and design
------------------------------

User_table
~~~~~~~~~~~
This table consists of a list of the system users' attributes with the following columns:

	- user_id
	- password
	- names
	- email
	- national_id
	- phone number
	- role

+--------------+--------------+------+-----+---------+----------------+
| Field        | Type         | Null | Key | Default | Extra          |
+--------------+--------------+------+-----+---------+----------------+
| user_id      | int(10)      | NO   | PRI | NULL    | auto_increment |
+--------------+--------------+------+-----+---------+----------------+
| password     | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| names        | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| email        | varchar(70)  | NO   | UNI | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| national_id  | varchar(255) | NO   | UNI | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| phone_number | varchar(255) | NO   |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+
| role         | int(1)       | NO   |     | 0       |                |
+--------------+--------------+------+-----+---------+----------------+


County_level_soh
~~~~~~~~~~~~~~~~~
This table consists of the county level SOH attributes. It has the following columns:

		- county              
		- report_period       
		- commodity           
		- pack_size           
		- agg_adj_consumption 
		- agg_soh             
		- mos               
		- zone  


+---------------------+-------------+------+-----+---------+-------+
| Field               | Type        | Null | Key | Default | Extra |
+---------------------+-------------+------+-----+---------+-------+
| county              | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| report_period       | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| commodity           | varchar(30) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| pack_size           | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| agg_adj_consumption | varchar(40) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| agg_soh             | varchar(30) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| mos                 | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| zone                | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+

Commodity_forecast_data
~~~~~~~~~~~~~~~~~~~~~~~~
This table consists of the commodity forecast attributes. It has the following columns:

	- commodity_forecast_data_id   
	- forecast_start_date          
	- forecast_period              
	- commodity_id                 
	- forecast_monthly_consumption


+------------------------------+-------------+------+-----+---------+----------------+
| Field                        | Type        | Null | Key | Default | Extra          |
+------------------------------+-------------+------+-----+---------+----------------+
| commodity_forecast_data_id   | int(25)     | NO   | PRI | NULL    | auto_increment |
+------------------------------+-------------+------+-----+---------+----------------+
| forecast_start_date          | varchar(15) | NO   |     | NULL    |                |
+------------------------------+-------------+------+-----+---------+----------------+
| forecast_period              | int(10)     | NO   |     | NULL    |                |
+------------------------------+-------------+------+-----+---------+----------------+
| commodity_id                 | varchar(25) | NO   | MUL | NULL    |                |
+------------------------------+-------------+------+-----+---------+----------------+
| forecast_monthly_consumption | varchar(20) | NO   |     | NULL    |                |
+------------------------------+-------------+------+-----+---------+----------------+


Current_stock
~~~~~~~~~~~~~~
This table consists of the current stock attributes. It has the following columns:

		- current_stock_id
		- commodity_id
		- quantity_received
		- quantity_issued
		- soh               

+-------------------+--------------+------+-----+---------+----------------+
| Field             | Type         | Null | Key | Default | Extra          |
+-------------------+--------------+------+-----+---------+----------------+
| current_stock_id  | int(25)      | NO   | PRI | NULL    | auto_increment |
+-------------------+--------------+------+-----+---------+----------------+
| commodity_id      | varchar(255) | NO   |     | NULL    |                |
+-------------------+--------------+------+-----+---------+----------------+
| quantity_received | int(255)     | NO   |     | NULL    |                |
+-------------------+--------------+------+-----+---------+----------------+
| quantity_issued   | int(255)     | NO   |     | NULL    |                |
+-------------------+--------------+------+-----+---------+----------------+
| soh               | int(255)     | NO   |     | NULL    |                |
+-------------------+--------------+------+-----+---------+----------------+

Pending_shipment_details
~~~~~~~~~~~~~~~~~~~~~~~~~
This table consists of pending shipment attributes. It has the following columns:

		 
		- pending_shipment_id
		- period
		- commodity_id
		- funding_agency_id
		- quantity
		- expected_time_of_arrival
		- comments
		- transaction_status

+--------------------------+--------------+------+-----+---------+----------------+
| Field                    | Type         | Null | Key | Default | Extra          |
+--------------------------+--------------+------+-----+---------+----------------+
| pending_shipment_id      | int(25)      | NO   | PRI | NULL    | auto_increment |
+--------------------------+--------------+------+-----+---------+----------------+
| period                   | int(10)      | NO   |     | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| commodity_id             | varchar(25)  | NO   | MUL | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| funding_agency_id        | int(25)      | NO   | MUL | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| quantity                 | varchar(25)  | NO   |     | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| expected_time_of_arrival | date         | NO   |     | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| comments                 | varchar(100) | NO   |     | NULL    |                |
+--------------------------+--------------+------+-----+---------+----------------+
| transaction_status       | varchar(20)  | NO   |     | pending |                |
+--------------------------+--------------+------+-----+---------+----------------+


Counties
~~~~~~~~~
This table consists of counties attributes. It has the following columns:

		- county_id
		- county_name
		- zone
		- comment


+-------------+--------------+------+-----+---------+-------+
| Field       | Type         | Null | Key | Default | Extra |
+-------------+--------------+------+-----+---------+-------+
| county_id   | varchar(20)  | NO   | PRI | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| county_name | varchar(30)  | NO   |     | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| zone        | varchar(20)  | NO   |     | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
| comment     | varchar(100) | NO   |     | NULL    |       |
+-------------+--------------+------+-----+---------+-------+

Central_level_data
~~~~~~~~~~~~~~~~~~~
This table consists of central level data attributes. It has the following columns:

		- central_level_stock_id
		- supply_agency_id
		- commodity_id
		- period
		- soh_closing_balance
		- funding_agency_id


+------------------------+-------------+------+-----+---------+----------------+
| Field                  | Type        | Null | Key | Default | Extra          |
+------------------------+-------------+------+-----+---------+----------------+
| central_level_stock_id | int(25)     | NO   | PRI | NULL    | auto_increment |
+------------------------+-------------+------+-----+---------+----------------+
| supply_agency_id       | int(25)     | NO   | MUL | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+
| commodity_id           | varchar(25) | NO   | MUL | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+
| period                 | varchar(25) | NO   |     | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+
| soh_closing_balance    | varchar(20) | NO   |     | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+
| funding_agency_id      | int(25)     | NO   | MUL | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+

Facility_level_data
~~~~~~~~~~~~~~~~~~~~
This table consists of facility level data attributes. It has the following columns:

		- central_drugs_id
		- drug_id
		- period
		- drug_category_id
		- drug_value
		- date


+------------------+-------------+------+-----+---------+----------------+
| Field            | Type        | Null | Key | Default | Extra          |
+------------------+-------------+------+-----+---------+----------------+
| central_drugs_id | int(11)     | NO   | PRI | NULL    | auto_increment |
+------------------+-------------+------+-----+---------+----------------+
| drug_id          | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| period           | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| drug_category_id | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| drug_value       | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| date             | varchar(30) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+

County_level_reporting_rates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
This table consists of county level reporting rates attributes. It has the following columns:

		- reporting_rate_id
		- reporting_rate_value
		- period
		- county_id
		- date

+----------------------+-------------+------+-----+---------+----------------+
| Field                | Type        | Null | Key | Default | Extra          |
+----------------------+-------------+------+-----+---------+----------------+
| reporting_rate_id    | int(11)     | NO   | PRI | NULL    | auto_increment |
+----------------------+-------------+------+-----+---------+----------------+
| reporting_rate_value | varchar(10) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+
| period               | varchar(10) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+
| county_id            | varchar(50) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+
| date                 | varchar(30) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+

Zones
~~~~~~~
The zones table has the following attributes:



		- zone
		- comment
		- zone_id

+---------+--------------+------+-----+---------+----------------+
| Field   | Type         | Null | Key | Default | Extra          |
+---------+--------------+------+-----+---------+----------------+
| zone    | varchar(30)  | NO   |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
| comment | varchar(100) | NO   |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
| zone_id | int(11)      | NO   | PRI | NULL    | auto_increment |
+---------+--------------+------+-----+---------+----------------+

Supply_chain_agencies
~~~~~~~~~~~~~~~~~~~~~~
The Supply chain agencies table has the following attributes:

		- supply_chain_agency_id
		- supply_chain_agency
		- contact_person
		- email
		- contact_phone
		- comment


+------------------------+---------------+------+-----+---------+----------------+
| Field                  | Type          | Null | Key | Default | Extra          |
+------------------------+---------------+------+-----+---------+----------------+
| supply_chain_agency_id | int(5)        | NO   | PRI | NULL    | auto_increment |
+------------------------+---------------+------+-----+---------+----------------+
| supply_chain_agency    | varchar(60)   | NO   |     | NULL    |                |
+------------------------+---------------+------+-----+---------+----------------+
| contact_person         | varchar(30)   | NO   |     | NULL    |                |
+------------------------+---------------+------+-----+---------+----------------+
| email                  | varchar(30)   | NO   |     | NULL    |                |
+------------------------+---------------+------+-----+---------+----------------+
| contact_phone          | int(55)       | NO   |     | NULL    |                |
+------------------------+---------------+------+-----+---------+----------------+
| comment                | varchar(1000) | NO   |     | NULL    |                |
+------------------------+---------------+------+-----+---------+----------------+


County_level_data
~~~~~~~~~~~~~~~~~
The county level data table has the following attributes:

		- county_drugs_id
		- county_id
		- drug_id
		- period
		- drug_category_id
		- drug_value
		- date

+------------------+-------------+------+-----+---------+----------------+
| Field            | Type        | Null | Key | Default | Extra          |
+------------------+-------------+------+-----+---------+----------------+
| county_drugs_id  | int(11)     | NO   | PRI | NULL    | auto_increment |
+------------------+-------------+------+-----+---------+----------------+
| county_id        | varchar(50) | NO   | MUL | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| drug_id          | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| period           | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| drug_category_id | varchar(20) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| drug_value       | varchar(15) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
| date             | varchar(30) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
		
Mapping_drugs_category
~~~~~~~~~~~~~~~~~~~~~~~
The Mapping drugs category table has the following attributes:

		- mapping_drugs_category
		- mapping_id
		- mapping_name


+------------------------+-------------+------+-----+---------+----------------+
| Field                  | Type        | Null | Key | Default | Extra          |
+------------------------+-------------+------+-----+---------+----------------+
| mapping_drugs_category | int(11)     | NO   | PRI | NULL    | auto_increment |
+------------------------+-------------+------+-----+---------+----------------+
| mapping_id             | varchar(20) | NO   |     | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+
| mapping_name           | varchar(50) | NO   |     | NULL    |                |
+------------------------+-------------+------+-----+---------+----------------+


Facility_level_reporting_rates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Facility level reporting  rates table has the following attributes:

			- reporting_rate_id
			- reporting_rate_value
			- period
			- date

+----------------------+-------------+------+-----+---------+----------------+
| Field                | Type        | Null | Key | Default | Extra          |
+----------------------+-------------+------+-----+---------+----------------+
| reporting_rate_id    | int(11)     | NO   | PRI | NULL    | auto_increment |
+----------------------+-------------+------+-----+---------+----------------+
| reporting_rate_value | varchar(10) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+
| period               | varchar(10) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+
| date                 | varchar(30) | NO   |     | NULL    |                |
+----------------------+-------------+------+-----+---------+----------------+

Funding_agenciebles
~~~~~~~~~~~~~~~~~
The funding agencies table has the following attributes:
  

		- funding_agency_id
		- funding_agency_name
		- comment

+---------------------+--------------+------+-----+---------+----------------+
| Field               | Type         | Null | Key | Default | Extra          |
+---------------------+--------------+------+-----+---------+----------------+
| funding_agency_id   | int(25)      | NO   | PRI | NULL    | auto_increment |
+---------------------+--------------+------+-----+---------+----------------+
| funding_agency_name | varchar(60)  | NO   |     | NULL    |                |
+---------------------+--------------+------+-----+---------+----------------+
| comment             | varchar(100) | NO   |     | NULL    |                |
+---------------------+--------------+------+-----+---------+----------------+

Facility_level_soh
~~~~~~~~~~~~~~~~~~~
The facility level SOH table has the following attributes:

		- Field
		- period
		- commodity_name
		- pack_size
		- agg_adj_consumption
		- agg_soh
		- mos
		- zone

+---------------------+-------------+------+-----+---------+-------+
| Field               | Type        | Null | Key | Default | Extra |
+---------------------+-------------+------+-----+---------+-------+
| period              | varchar(10) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| commodity_name      | varchar(30) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| pack_size           | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| agg_adj_consumption | varchar(30) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| agg_soh             | varchar(40) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| mos                 | varchar(20) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+
| zone                | varchar(30) | NO   |     | NULL    |       |
+---------------------+-------------+------+-----+---------+-------+


Malaria_commodities
~~~~~~~~~~~~~~~~~~~~
The malaria commodities table has the following attributes:

		- commodity_id
		- commodity_name
		- alt_name
		- unit_of_measure
		- commodity_description

+-----------------------+--------------+------+-----+---------+-------+
| Field                 | Type         | Null | Key | Default | Extra |
+-----------------------+--------------+------+-----+---------+-------+
| commodity_id          | varchar(25)  | NO   | PRI | NULL    |       |
+-----------------------+--------------+------+-----+---------+-------+
| commodity_name        | varchar(60)  | NO   |     | NULL    |       |
+-----------------------+--------------+------+-----+---------+-------+
| alt_name              | varchar(255) | NO   |     | NULL    |       |
+-----------------------+--------------+------+-----+---------+-------+
| unit_of_measure       | varchar(15)  | NO   | MUL | NULL    |       |
+-----------------------+--------------+------+-----+---------+-------+
| commodity_description | varchar(100) | NO   |     | NULL    |       |
+-----------------------+--------------+------+-----+---------+-------+

Planned_procurement_details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The planned procurement details has the following attributes:

		- planned_procurement_id
		- commodity_id
		- unit_of_measure
		- quantity
		- planned_delivery_date
		- funding_agency_id
		- comment

+------------------------+--------------+------+-----+---------+----------------+
| Field                  | Type         | Null | Key | Default | Extra          |
+------------------------+--------------+------+-----+---------+----------------+
| planned_procurement_id | int(11)      | NO   | PRI | NULL    | auto_increment |
+------------------------+--------------+------+-----+---------+----------------+
| commodity_id           | varchar(25)  | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
| unit_of_measure        | varchar(15)  | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
| quantity               | varchar(25)  | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
| planned_delivery_date  | varchar(15)  | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
| funding_agency_id      | int(25)      | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
| comment                | varchar(100) | NO   |     | NULL    |                |
+------------------------+--------------+------+-----+---------+----------------+
