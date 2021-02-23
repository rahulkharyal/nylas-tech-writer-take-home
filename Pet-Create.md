# Pet Creation

## Objective

In this application, we will be learning how to create a new Pet.

## Introduction

This part of the application is make sure that a new pet can be created by using the application with all the required parameters.

## Table of Contents
* [Definitions](#definitions)
	* [Pet-Create Document](#pet-create-document)
	* [HTTP Status Codes](#http-status-codes)
* [Specification](#specification)
	* [Format](#format)
	* [Document Structure](#document-structure)
	* [Data Types](#data-types)
	* [Schema](#schema)
		* [Pet Create Object](#pet-create-object)
		* [Status Object](#status-object)
		* [Security Requirement Object](#security-requirement-object)

## Definitions

### Pet-Create Document

A document that defines and or describes the creation of pets in the system. This definition uses and conforms to the requirement specification  

### HTTP Status Codes

The HTTP Status Codes are used to indicate the status of the executed operation. The available status codes are defined by tech-writer-take-home assignment and are listed in the Coding Best Practices.

## Specification

### Format

-	A pet creation document, which shows you how to create a pet using the application. The records are stored in a database in json format.

### Document Structure

The structure of this document can be used as a whole to learn the pet creation module of the application.

### Data Types
|  Common Name  |    type    |   format   |					Comments					|
| --- | --- | --- | ----- |
| string | String | NA | Information received in the form of text |


### Schema

In the following description, if a field is not explicitly mentioned as **REQUIRED**, it can be considered as OPTIONAL. 

#### Pet Create Object


##### Fixed Fields
|  Field Name  |    Type    |   Values   |					Description					|
| --- | --- | --- | ----- |
| category | Object | NA | An object that records parametric values |
| name | String | NA | **REQUIRED.** A string to store a category name of a pet |
| prop1 | String | NA | A string to describe a sub category for a pet |
| name | String | NA | **REQUIRED.** A string to record name of a pet |
| photoUrls | String | NA | A string value for a link to the photo of a pet|
| tags | Object | NA | An object to tag a pet|
| name | String | NA | **REQUIRED.** A string to register a tag name of a pet|
| status | String | NA | A string to show the booking/availability status of a pet|
| petType | String | NA | A string to show the type of a pet, e.g. cat, dog, fish and rabbit|

##### Pet Create Object Example

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


#### Status Object

A description of the returned result status with the correct error code or successful operation code

| Code | Description |
| --- | --- |
| 200 | New pet created! |
| 405 | Invalid Input! |

#### Security Requirement Object

This specifies the security schemes to execute this operation. Security Requirement Object specifies that bearer authorization needs to be implemented to access or modify records of pets in the database.


#### Security Requirement

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

| Authorization | Description |
| --- | --- |
| write | Access the pets database to edit or modify records |
| read | Access the pets database to access all records |




