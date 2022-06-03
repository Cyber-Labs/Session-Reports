# Session 3
*Topic:* ViewBinding and DataBinding

*Conducted on:* 08-06-2021 21:00

## Agenda
A Session on implementation of ViewBinding and DataBinding

## Summary

Repo For reference -- https://github.com/mrinalpathak16/RecyclerViewDemo

A practical class on implementing viewbinding and databinding to optimize code in refrence repo.

### Important concepts discussed :

#### changes made in grade
     android {
    ...
    buildFeatures {
        viewBinding true
      }
    }

#### Binding class
    By default, a Binding class will be generated based on the name of the layout file(xml file)
    with which we can implement data binding and view binding.
#### View binding
    View Binding is the feature by which we bind views with the activity which is ongoing,
    i.e, binding the views of the layout file with the java code and hence replacing the findViewById() method
    For syntax refer resource links.
#### Data binding
    This support library allows to bind UI components in your layouts to data sources in your app using declarative format.
    for syntax refer resources.
#### reforming the xml structure to use data binding
    <layout>
    <data>
        <variable
            name="--any_name--"
            type="--modelclass--" /> 
            <!--add as much variables as you want -->
    </data>
    <ConstraintLayout... /> <!-- UI layout's root element(any root element can work) -->
    </layout>
#### Attribute used while data binding
* @{} or @={}
used to refer to data element. 
#### lambda function
    Used to bind the method refrence in the xml(layout) file.
  @{() -> presenter.showList()} in this presenter.show() represents the method call and ()-> is the syntax for gamma function.
    
#### Binding adapter
They are responsible for making appropriate framework calls to set values.
    refer to https://developer.android.com/topic/libraries/data-binding/binding-adapters#java
    

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

*Conducted by*: Bhavesh Sharma

*Report compiled by*: Tarun Shrivastava 

*Attendees*: Abdullah, Anisha Dutta, Ansh Tandon, Bhavya Agarwal, Ganta Nikhil, Garvit Dua, Saurav Kumar, Tarun Shrivastava


