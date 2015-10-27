# Primary Schools API
### Data Representation and Querying Project 2015
### Created by: Will Hogan, 3rd year Software Development, GMIT Galway

## Overview
As a required part of my 3rd year project for module Data Representation & Querying, in GMIT Galway, I have created an API which Allows developers to connect and retrieve information from the above URL. The details i feel will be extremely useful as it holds a complete list of Primary Schools in Ireland, plus all other associated relevant data. 

This project provides the design and documentation for the dataset "Primary-and-Special-Schools-List-2014-2015" which is available at this URL: [data.gov.ie](http://www.education.ie/en/Publications/Statistics/Data-on-Individual-Schools/Data-on-Individual-Schools.html). 

## Information about the Dataset
The data itself is in CSV format (Comma Separated Values), which was obtained from [Data-on-Individual-Schools](http://www.education.ie/en/Publications/Statistics/Data-on-Individual-Schools/Data-on-Individual-Schools.html).You will need to look for the heading within this page called "Primary All Schools" 

###Size, Fields & Values
The file contains 3138 unique rows. Each row has 17 fields with associated values. 
Here is a breakdown of each field:

|  Field   | Value  |
|:--------:|:-------------------------------------------:|
| **County Name**        | The name of the Country |
| **Local Authority Desc**        | Local Co.Council name |
| **Roll No.** | ID Number | 
| **Official School Name** | The Official name of the school                    |
| **Address Line 1** | Address |
| **Address Line 2** | Address Continued |
| **Address Line 3** | Address Continued|
| **Address Line 4** | Address Continued|
| **Phone Number** | Phone contact number |
| **Email Address** | Email information|
| **Ethos/Religion Desc** | Religious persuasion of the School |
| **Island Ind (Y/N)** | Is the Island in question Independent |
| **Irish Classification Description** | If taught through Irish or not  |
| **DEIS (Y/N)** |  Deis, y/n |
| **Total Boys** |  Total Boys in the school |
| **Total Girls** | Total Girls in the school | 
| **Total Pupils** | Total Pupils in the school  |


##Design & URL's
My API was designed to be made accessible to anyone looking for information regarding Primary Schools in Ireland. This has been made possible by connecting with the [data.gov.ie](https://data.gov.ie/data) website and using my API as the interface to retrieve the information. 

####Using the provided URL's
With this API, you can get a list returned in JSON format using the GET method at the following URL:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/[name] ``` 
where the _name_ section of the url, requires the users input. 
So for example if we type in Carlow instead of the [name], the URL will change to this:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/Carlow ``` and will return a list of schools in Co Carlow, with the following properties for each one:
- **County Name**: The name of the Country 
- **Local Authority Desc**: Local Co.Council name
- **Roll No.**: The Role ID Number  
- **Official School Name**: The Official name of the school                    
- **Address Line 1**: Address of the School 
- **Address Line 2**: Address Continued 
- **Address Line 3**: Address Continued
- **Address Line 4**:Address Continued
- **Phone Number**: Phone contact number 
- **Email Address**: Email information
- **Ethos/Religion Desc**: Religious persuasion of the School 
- **Island Ind (Y/N)**: Is the Island in question Independent 
- **Irish Classification Description**: If taught through Irish or not 
- **DEIS (Y/N)**: Deis, y/n
- **Total Boys**: Total Boys in the school
- **Total Girls**: Total Girls in the school
- **Total Pupils**: Total Pupils in the school

Here's an example of a response in JSON format
```json
[
  {
    "County Name":"Carlow",
    "Local Authority Desc":"Carlow County Council",
    "Roll No.":"00651R",
    "Official School Name":"BORRIS MXD N S",
    "Address Line 1":"BORRIS",
    "Address Line 2":"CO CARLOW",
    "Address Line 3":"",
    "Address Line 4":"",
    "Phone Number":599773402,
    "Email Address":"borrismixedns@gmail.com",
    "Ethos/Religion Desc":"CATHOLIC",
    "Island Ind (Y/N)":"N",
    "Irish Classification Description":"No Irish",
    "DEIS (Y/N)":"N",
    "Total Boys":"104",
    "Total Girls":"103",
    "Total Pupils":"207"
  }
]
```

####Other type of search options
Likewise if we change the search criteria at this URL:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/TaughtThroughIrish/[No Irish/All+Irish] ``` 

To search for:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/TaughtThroughIrish/All+Irish ```
The reponse will contain all rows where the school ciriculum is taught through Irish. 

A sample response would look like this:
```json
[
  {
    "County Name":"Galway",
    "Local Authority Desc":"Galway City Council",
    "Roll No.":"19858V",
    "Official School Name":"GAELSCOIL DARA",
    "Address Line 1":"B�THAR BHAILE AN LOCH�IN",
    "Address Line 2":"AN RINN MH�R",
    "Address Line 3":"GAILLIMH",
    "Address Line 4":"",
    "Phone Number":91757145,
    "Email Address":"gaelscoildara.ias@eircom.net",
    "Ethos/Religion Desc":"CATHOLIC",
    "Island Ind (Y/N)":"N",
    "Irish Classification Description":"All Irish",
    "DEIS (Y/N)":"N",
    "Total Boys":"188",
    "Total Girls":"233",
    "Total Pupils":"421"
  }
]
```

