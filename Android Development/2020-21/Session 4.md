# Session 4
*Topic:* Retrofit

*Conducted on:* 16-06-2021 19:00

## Agenda
A Session on understanding and implementation of Retrofit

## Summary

//Repo For reference -- https://github.com/mrinalpathak16/RecyclerViewDemo

//A practical class on implementing Retrofit to intigrate an API in the project present in refrence repo.

### Important concepts discussed :

#### changes made in grade(dependencies for Retrofit)
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'

#### changes made in manifest file
    <uses-permission android:name="android.permission.INTERNET"/>

#### Source of JSON data
    https://jsonplaceholder.typicode.com/

#### Who handles which part of project:
    Frontend -> Web/App Developer
    Backend -> Web Developer
    Database -> Web Developer

#### Data Interaction:
    Frontend -> Requests to Backend <-> Database -> Response to Frontend 
#### All about API
    API = Application Programming Interface
    Here we are refering only web APIs.

    API Development -> Backend Web Developer
    Frontend Developers(We) -> Consumes API

    Parts of API -> URL, Request Format, Response Format.
    
    An API URL have 2 parts :
    Base URL (https://jsonplaceholder.typicode.com ) + Route (/post , /comments , etc.)


#### JSON
    JSON = JavaScript Object Notation

    {
        "title" : "Sea Food",
        "blog-content": "I had a nice time experiencing sea food at XYZ restaurent!"
        "likes": 5,
        "date-created": "2021-06-16",
        "tags": ["cuisine","travelling","blog"]
    } 


#### Request Types ->

    GET = Fetch certain data based on some parameters.
    POST = Send some data for including into database.
    (Above are the mainly used request types.)
    PATCH, PUT, DELETE

#### Steps to integrate API in a project->

    * Get the URL, request format, response format
    * Test it on Postman
    * Create Response Model Class(and Request Model Class in case of POST requests)
    * Define an Interface-> function (request type (GET, POST), request model, response model).
    * Instantiate a Retrofit and the interface.
    * Call the API.
#### What exactly Retrofit does?
    Retrofit -> Requests response -> use GSON Converter Factory to convert response into Java Object .


### Resources provided :

Articles:

* Retrofit -- https://futurestud.io/tutorials/retrofit-getting-started-and-android-client


# Credits

*Conducted by*: Akash Mahapatra and Bhavesh Sharma

*Report compiled by*: Abdullah

*Attendees*: Abdullah, Anisha Dutta, Ansh Tandon, Bhavya Agarwal, Ganta Nikhil, Garvit Dua, Saurav Kumar, Tarun Shrivastava




