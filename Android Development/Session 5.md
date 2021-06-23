# Session 5

_Topic:_ View Model and Live Data

_Conducted on:_ 21-06-2021 20:30

## Agenda

A Session on implementation of View Model and Live Data

## Summary

Repo For reference -- https://github.com/bhavesh3005sharma/android-mvvm-architecture

A class on implementing View Model and Live Data to store and access Data efficiently.

### Important concepts discussed :

#### View Model Class

    ViewModel helper is responsible for preparing data for the UI. ViewModel objects are automatically retained during configuration changes so that data they hold is immediately available to the next activity or fragment instance without any loss.

#### Implementing View Model

##### Code for Model Class

    public class MyViewModel extends ViewModel {

        // Any variable private or public are declared here.

        private void any_funtion() {

        }
    }

##### Accesing View Model elements from an activity

    public class MyActivity extends AppCompatActivity {
    public void onCreate(Bundle savedInstanceState) {

        MyViewModel model = new ViewModelProvider(MyActivity.this).get(MyViewModel.class);

        // To access variable/funtion.
        model.{Variable or Funtion of Model class};
    }

}

#### Live Data

Live Data is an observable Data Holder Class
It is not Mutable

- Declaration :-
  public final LiveData<Class_Name> liveData = new LiveData<>();

_To Observe the data in liveData We use observe funtion_

#### Mutablelive Data

Mutablelive Data is an sub class of Live Data.
It is Mutable (Can be Modified or Changed).

### Important Notes:-

- Do not Reinitialize the Arraylist (Any List) , Always use clear() and add() funtions.
- Do not set adapter again and again use notifyDataSetChanged() to notify about changed data in list.

### Resources provided :

Videos:

- https://www.youtube.com/watch?v=i22jxmIh_EE

Articles:

- Viewmodel :- https://developer.android.com/topic/libraries/architecture/viewmodel

- LiveData :- https://developer.android.com/reference/android/arch/lifecycle/LiveData

- MutableLiveData :- https://developer.android.com/reference/android/arch/lifecycle/MutableLiveData

--Reference Repo for Live Data :-
https://github.com/trulymittal/viewModel_LiveData/tree/starter_project

# Credits

_Conducted by_: Bhavesh Sharma , Pratham Pahariya

_Report compiled by_: Bhavya Agrawal

_Attendees_: Abdullah, Anisha Dutta, Ansh Tandon, Bhavya Agarwal, Ganta Nikhil, Garvit Dua, Tarun Shrivastava
