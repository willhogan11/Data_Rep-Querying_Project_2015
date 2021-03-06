# Primary Schools API

- **Project Heading:** Software Development Project for 3rd year subject Data Representation and Querying
- **Title:** Primary Schools API
- **Created:** By Will Hogan
- **Submission Date:** 13th November 2015, 5pm
- **Third Level Establishment:** GMIT, Galway, Ireland

## Overview
As a required part of my 3rd year project for module Data Representation & Querying, in GMIT Galway, I have created an API which Allows developers to connect and retrieve information from the above URL. The details i feel will be extremely useful as it holds a complete list of Primary Schools in Ireland, plus all other associated relevant data. 

This project provides the design and documentation for the dataset "Primary-and-Special-Schools-List-2014-2015" which is available at this URL: [data.gov.ie](http://www.education.ie/en/Publications/Statistics/Data-on-Individual-Schools/Data-on-Individual-Schools.html). 

For reference, i have attached the following files:
- ```Primary-and-Special-Schools-List-2014-2015.json```
- ```Primary-and-Special-Schools-List-2014-2015.csv```
- ```xmlSample.xml```


## Information about the Dataset
The data extracted form the website itself is in CSV format (Comma Separated Values), which was obtained from [Data-on-Individual-Schools](http://www.education.ie/en/Publications/Statistics/Data-on-Individual-Schools/Data-on-Individual-Schools.html).You will need to look for the heading within this page called "Primary All Schools". 


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

The data format returned, can be either JSON or XML. The examples provided in this API, focus primarily on JSON format, however just to illustrate, i have included a sample xml response also.  

####Using the provided URL's
With this API, you can get a list returned in JSON format using the POST(Preferred) or GET method at the following URL:
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

Here's an example of one of the response rows in JSON format
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

And the equivalent in XML format:
```xml
<ROW>
	<County Name>Carlow</County Name>
	<Local Authority Desc>Carlow County Council</Local Authority Desc>
	<Roll No.>00651R</Roll No.>
	<Official School Name>BORRIS MXD N S</Official School Name>
	<Address>
		<Address Line 1>BORRIS</Address Line 1>
		<Address Line 2>CO CARLOW</Address Line 2>
		<Address Line 3></Address Line 3>
		<Address Line 4></Address Line 4>
	</Address>
	<Phone Number>599773402</Phone Number>
	<Email Address>borrismixedns@gmail.com</Email Address>
	<Ethos/Religion Desc>CATHOLIC</Ethos/Religion Desc>
	<Island Ind (Y/N)>N</Island Ind (Y/N)>
	<Irish Classification Description>No Irish</Irish Classification Description>
	<DEIS (Y/N)>N</DEIS (Y/N)>
	<Totals>
		<Total Boys>104</Total Boys>
		<Total Girls>103</Total Girls>
		<Total Pupils>207</Total Pupils>
	</Totals>
</ROW>
```

####Sample Search Options
Likewise if we change the search criteria at this URL:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/TaughtThroughIrish/[No Irish/All&Irish] ``` 

To search for:
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/TaughtThroughIrish/All&Irish ```
The reponse will contain all rows where the school ciriculum is taught through Irish. 

A sample Row returned in JSON format would look like this:
```json
[
  {
    "County Name":"Galway",
    "Local Authority Desc":"Galway City Council",
    "Roll No.":"19858V",
    "Official School Name":"GAELSCOIL DARA",
    "Address Line 1":"BÓTHAR BHAILE AN LOCHAIN",
    "Address Line 2":"AN RINN MHÓR",
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

To search for a particular school: 
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/SchoolName/Ennistymon&National&School ```
The reponse will contain a row with the School name 

A sample response would look like this:
```json
[
  {
    "County Name":"Clare",
    "Local Authority Desc":"Clare County Council",
    "Roll No.":"20245S",
    "Official School Name":"Ennistymon National School",
    "Address Line 1":"Ennistymon",
    "Address Line 2":"Co. Clare",
    "Address Line 3":"",
    "Address Line 4":"",
    "Phone Number":null,
    "Email Address":"etynns@gmail.com",
    "Ethos/Religion Desc":"CATHOLIC",
    "Island Ind (Y/N)":"N",
    "Irish Classification Description":"No Irish",
    "DEIS (Y/N)":"Y",
    "Total Boys":"56",
    "Total Girls":"60",
    "Total Pupils":"116"
  }
]
```

##HTTP methods and Examples
In this section i will be covering some examples of how to use HTTP methods with this API. 
Firstly, here is a breakdown of each sub part of a sample URL, mentioned earlier; ``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/[name] ```

|  URL Section     | Explanation  |
|:----------------:|:-------------------------------------------:|
| http  | Protocol being used |
| www        | SubDomain |
| education.ie | Domain | 
| en/Publications/Statistics/PrimarySchools/county/name/ | Path |  
| [name] | The Search Criteria |


####POST Example
This example outlines the requirements for posting a new record, in this case a new School
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/new ```

####Request Body Example
This is a partial view of how the request body should look like;
```
POST /en/Publications/Statistics/PrimarySchools/county/name/schoolName.html / HTTP/1.1
host: www.education.ie
id=304&CountyName=Galway&LocalAuthorityDesc&=Galway&country&council&OfficialSchoolName=Scoil&Mhuire ... and so on 
...
```
####POST Example for retrieval 
This is an example of how to retrieve information with a POST method, where the number appended to the end of the URL is the id number.
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/get/304 ```

####GET Example
This is another example that details the requirements for a GET request, with the same idea as with POST. 

**NOTE: I would strongly discourage the use of this method in this fashion, opting instead for the ```POST``` method, mentioned above. You can send a request body with GET but it should not have any meaning. If you give it meaning by parsing it on the server and changing your response based on its contents you're violating the HTTP/1.1 spec. **

Here is the example;
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/get/304 ```

####PUT Example
Here is an example of how to update a record, using the PUT method
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/put/304 ```

####Request Body Example
And here is the request body, note the School name has been edited;
```
PUT /en/Publications/Statistics/PrimarySchools/county/name/schoolName.html / HTTP/1.1
host: www.education.ie
OfficialSchoolName=Scoil&Mhuire&Naofa
...
```

####DELETE Example
``` http://www.education.ie/en/Publications/Statistics/PrimarySchools/county/name/delete/304 ```

####Request Body Example
This is a sample DELETE operation request;
```
DELETE /en/Publications/Statistics/PrimarySchools/county/name/schoolName.html / HTTP/1.1
host: www.education.ie
id=304
...
```

####Conclusion
As outlined above and as one can see, this API contains as much information as is relevant for the Software Developer to be able to work with. I have made this README file easy to read, with Headings, links and a comprehensive breakdown of file formats and general information relevant to the topic. 

I hope that anyone using this finds it useful. 
