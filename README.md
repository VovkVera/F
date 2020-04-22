# Python test task #

## Brief ##

You have to implement minimalistic Django application with admin interface and one REST endpoint. Important: before starting implementation you should read carefully Requirements paragraph and do the task accordingly to it.  

## Description ##
### General ### 
Module should be designed for analysis of discount conditions between partner companies.  
Notion 1 - Discount Agreement (Agreement)</br>
Notion 2 - Period of agreement (Period)</br>
Notion 3 - Company</br>
Notion 4 - Country </br>
Notion 5 - Responsible person (Negotiator)</br>

Agreement has start and stop date, company agreement concluded with, responsible person - negotiator, debit and credit turnover (export/import). </br>
Period - start and stop date, status - described below. One agreement can have several periods inside. Inside agreement periods should not intersect. Agreement start date could be earlier than start date of the earliest period (but not vice versa) as well as agreement stop date could be later than stop date of the latest period (but not vice versa).</br>
Company - title, country.</br>
Country - 3-alpha iso code, name</br>
Negotiator - user who is responsible for agreement. Should be a django user as well.</br>
Status - state of a period. Could be: New, Active, Reconciliation, Closed </br>
### Admin interface ###
Each object should be represented in Django admin. You need to provide search, filters etc guided by your understanding of usability. Agreement should display Periods with tabular inline.</br>
### UI ###
On the index page there should be link to the django admin only.</br>
### API ###
You have to implement API for agreement calendar.</br>
Number displayed in a month block means number of agreements that are closing this month. Agreement is closing this month if stop date of latest period is in this month.</br>
/agreements/calendar/ - sample JSON response: </br>
 > { </br>
  >      2017: [0, 0, 0, 0, 0, 0, 0, 0, 12, 1, 0, 5],</br>
  >      2018: [1, 0, 0, 4, 0, 0, 0, 1, 7, 10, 0, 4] </br>
>  }
</br>
2017 and 2018 are years. Arrays - index means month number, digit - number of closing agreements.
</br>
Endpoint should support following filters: country, negotiator, company. 
For example: </br>
> ?country=1,2,7&negotitator=4,8 Number is an id of an object. </br>

## Requirements ##
### General ###
Provide fixtures that contain test data: several agreements with several periods </br>
### Will be a plus ###
Unit tests </br>
Coding style </br>
Code should correspond to industrial standards: pep8, pylint et al. </br>
## Results ##
You need to provide information about hours spent on this task, preferrably with split by subtasks.
