#Objective

In this application, we will be learning how to create a new Pet.

#Introduction

This part of the application is make sure that a new pet can be created by using the application with all the required parameters.

#Table of Contents

*Definitions

*Specification
	

##Definitions

#Specification

##Format

-	A pet creation document  with file format JSON

## Document Structure

The structure of this document can be used as a whole to learn the pet creation module of the application.

##Data Types
|  Field Name  |    Type    |   Values   |					Descrption					|
| --- | --- | --- | ----- |
| category | Object | An object that records parametric values |
| name | String | NA | A string to store a category name of a pet |
| prop1 | String | NA | A string to describe a sub category for a pet |
| name | String | NA | A string to record name of a pet |
| photoUrls | String | A string value for a link to the photo of a pet|
| status | String | A string to show the booking status of a pet|
| petType | String | A string to show the type of a pet, e.g. cat, dog, fish and rabbit|


# Pet Create Object


##Fixed Fields
|  Field Name  |    Type    |   Values   |					Descrption					|
| --- | --- | --- | ----- |
| category | Object | An object that records parametric values |
| name | String | NA | A string to store a category name of a pet |
| prop1 | String | NA | A string to describe a sub category for a pet |
| name | String | NA | A string to record name of a pet |
| photoUrls | String | A string value for a link to the photo of a pet|
| status | String | A string to show the booking status of a pet|
| petType | String | A string to show the type of a pet, e.g. cat, dog, fish and rabbit|

##Pet Create Object Example

```
	{
  	"category": { //what category the pet belongs to
    	"name": "string", //category name
    	"sub": {
      	"prop1": "string" //maybe a sub category for the pet
    	}
  	},
  	
		"name": "Guru", //pet name
  	"photoUrls": [
    	"string" // phots of the pet. We aren't going to store images, so provide a URL
  	],
  	
		"tags": [
    	{
      	"name": "string" //let them provide their tags as a way to organize the pets
    	}
  	],
  
		"status": "available", //is the pet avail for adoptions. can also have pending_adoption and adopted.
  	"petType": "cat", //what type of pet. Let's start with cat, dog, rabbit and fish. add more as we get feedback.
	}

```

```
		category:
    	name: Sample category name
    	sub:
				prop1: Sample sub category of pet
  	
		name: Guru
  	photoUrls: http://www.photos.google.com
  	
		tags:
				name: Woofey
  
		status: available 
  	petType: dog

```


##Returns Object

A description of the returned result with the correct error code or successful operation code

| Code | Decription |
| --- | --- |
| 200 | New pet created! |
| 405 | Invalid Input! |

##Security Requirement Object

This specifies the security schemes to execute this operation. Security Requirement Object specifies that bearer authorization needs to be implemented to access or modify records of pets in the database.


Security Requirement

```
{
  "bearer_auth": [
    "write:pets",
    "read:pets"
  ]
}
```

```
bearer_auth:
	- write:pets
	- read:pets

```

| Authorization | Decription |
| --- | --- |
| write | Access the pets database to edit or modify records |
| read | Access the pets database to access all records |




