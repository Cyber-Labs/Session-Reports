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

An API URL have 2 parts :
Base URL (https://jsonplaceholder.typicode.com ) + Route (/post , /comments , etc.)

### Changes in the repo after class :

Commit after session completion -- https://github.com/mrinalpathak16/RecyclerViewDemo/pull/1/commits

Commit message -- "View Binding & Data Binding Added".

### Resources provided :

Videos:

* ViewBinding -- https://www.youtube.com/watch?v=9Ga1lZ-Xn24

* ViewBinding with RecyclerView -- https://www.youtube.com/watch?v=04l3vAR4IBE

* DataBinding -- https://www.youtube.com/watch?v=tDYZBSSgp1c

* DataBinding with RecyclerView -- https://www.youtube.com/watch?v=0eV7iB109ME

Articles:

* ViewBinding -- https://www.raywenderlich.com/6430697-view-binding-tutorial-for-android-getting-started

* View Binding -- https://developer.android.com/topic/libraries/view-binding#:~:text=%20To%20set%20up%20an%20instance%20of%20the,the%20active%20view%20on%20the%20screen.%20More%20 

* Intro to data binding -- https://developer.android.com/topic/libraries/data-binding

* Various techniques of data binding as discussed in class --  https://www.vogella.com/tutorials/AndroidDatabinding/article.html#:~:text=Android%20offers%20support%20to%20write%20declarative%20layouts%20using,a%20data%20element%20and%20a%20view%20root%20element .



# Credits

*Conducted by*: Akash Mahapatra and Bhavesh Sharma

*Report compiled by*: Abdullah

*Attendees*: Abdullah, Anisha Dutta, Ansh Tandon, Bhavya Agarwal, Ganta Nikhil, Garvit Dua, Saurav Kumar, Tarun Shrivastava




