# Data Warehouse simulation

We have analyzed a TukTuk company and implemented a data warehouse with the use of PostGreSQL and Pentaho Data Integration tools. We had to make some decisions, which data to put into facts and which into dimensions. It is important to point out, that some data could later be moved from dimension to fact or vice-versa.

We are using star schema.
There are 2 facts and 5 dimensions. Besides that, we also have a principle of role-playing dimensions. Service fact uses 3 views from Date dimension (requested, initialized and transport date) and 2 views from Location dimension (address, destination).
Client dimension uses minidimension, for the yearly income and age values, as the first can change often and the second changes once a year.
Drives fact is a factless fact table, as it only contains keys for other dimensions. We can use count function if we want to know how many drivers can drive a car or how many cars a driver is registered to. Drives could also be a dimension instead of a fact. But we envisioned a company, that often changes vehicles and possibly does more shifts per day, therefore driver-tuktuk relation can be changed very often.
