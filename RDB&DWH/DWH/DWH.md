# OLTP vs OLAP database

__Online Transaction Processing (OLTP)__
- the use of the database is characterized by many small actions
- are often normalized, prevents redundancy and increases data consistency

__Online Analytical Processing (OLAP)__
- use is mainly characterised by reading larger datasets, often to make reports
- workload does not benefit form normalization, rather opposite. More tables make querries more complicated and slower.
- Indexes make reading faster but writing slower. good for OLAP


# Why build DWH?
- To solve performance related problems
- Solve quality related problems

## Goals of DWH
- Reporting
- Analysis of events in the past or actual events
- Predictions based on trend analysis
- Multidimensional reporting
- Empowerment of end user by offering simplified reporting tools
- Data mining

# Advantages of DWH
__High ROI__
- Large investments with potentials high ROI after short period
__Competitive advantages__
- Acces to data that was not available, unkown or unused before
__Increased productivity of corporate decision makers__

# Problems associated with DWH
__Underestimation of resources (costs) for ETL__
- Extraction, transformation, and loading data in DWH takes lots of time 
- projects might take years

__Hidden problems with source systems__
- sometimes only discoverd after years

__Required data not captured__
- change actual system or develop seperate system for those data

__Increased end-user demands__
- Enhanced load of IT personnel
- beter end user training

__Data homogenization__
- Trying to focus on similarities between data might lover the use of data

__High demand for resources__
- disk space

__Data ownership__
- sensitive data must be highly secured

__High maintenance__
- each change influences the DWH

__Long projects__
- Development can take years

__Makes expectation of user 'empowering'__
- make own reports

__Complexity of integration__
- Different DWH tools have to work together

__Complex change and version management__

# DWH components
![[Pasted image 20250107211340.png]]

## Data mart
=> DB existing of subset of company data to support the needs of a particular business unit for data analysis or to support users sharing the same needs for analyzing business processes.

__Why?__
- To give users acces data they use most frequently
- Offer data in way that corresponds to collective view of a group user in department
- imporve response time 
- offer data in format that fits the tools
- reduction of complexity
- reduction of cost


