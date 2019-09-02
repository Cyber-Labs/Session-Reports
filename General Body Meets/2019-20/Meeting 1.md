# Meeting 1

Discussion on Project Proposals

Conducted on : 01-09-2019, Sunday

## Agenda

Discussions on Project Proposals and finalising projects to be done in Phase 1

## Resources

N/A

## Summary

Following Project Proposals were discussed with respect to feasibility, user-base and resources required : 

| Sr No. |  Projects                                            |   Required Divisions |
| ------ | ---------------------------------------------------- | -------------------- |
| 1.     |  Neural Style Transfer on Videos                     |   ML+Android         |
| 2.     |  QnA enquiry system for IIT(ISM)                     |   ML+Web+Android     |
| 3.     |  Diagnosing of Diseases using Medical Imaging        |   ML+Web+Android     |
| 4.     |  Barber Booking App                                  |   ML+Web+Android     |
| 5.     |  Krishi App for Farmers                              |   ML+Android         |
| 6.     |  Garbage Collecting Bot                              |   ML+Web+Hardware    |
| 7.     |  Appearance & Pose-Conditioned Human Image Generation|   ML                 |
| 8.     |  mManager                                            |   Android            |
| 9.     |  Medical History                                     |   Web+Android+ML+DL  |
| 10.    |  Gameplan                                            |   ML+Web             |
| 11.    |  DietPlus                                            |   ML+Android         |
| 12.    |  Home Automation System                              |   Hardware+Web+App   |
| 13.    |  Campus Selection System                             |   ML+Web             |
| 14.    |  IIT(ISM) Library Search                             |   Web+Android        |
| 15.    |  NoPhishing                                          |   Web+ML+Security    |
| 16.    |  Single Image Super Resolution                       |   ML                 |
| 17.    |  Timelining                                          |   ML+Web+Android     |

### The following projects were finalized: 

1. #### QnA enquiry system for IIT(ISM)

**Project Title**: QnA IIT(ISM) <br />
**Proposed by**: Saloni Mohta, Anjali R Pahal <br />
**Required Divisions**: Web+Android+ML <br />
**Details**: <br />
    **Description**: <br />
    An application for our College only, which suggests solutions to certain problems faced by all, be it academics related, career related, admin related, campus related etc. An inner quora basically with categories like social issues, admin issues, academic issues, where a person writes about their problem, how did they tackle it or whom did they approach for the problem, how was it solved etc. 
    <br />**Features**: <br />
    1. General questions like how to learn a particular language or about Restaurants in Dhanbad etc. should not be asked which is not specific to the college. The app should notify the user that this question is not specific to college. 
    <br /> 2. When question is answered the app should ask the user to either approve it or say not relevant. <br />
    3. Answers should include points like: <br />
        3.1 Duration required for the problem to be solved. <br />
        3.2 Whom did you approach. <br />
        3.3 List of all the ways user tried to get rid of the problem and it's outcomes. <br />

**Link to similar work**: Quora can be referred.

**Major Tech stacks/skills required**: 
   
   1. ML :
       <br /> 1.1 For semantic similarity: MT+DNN / BERT
      <br />  1.2 For question category classification: MT-DNN / BERT
      <br />  1.3 A virtual/real GPU machine will be required
    <br /> 2. Web : 
       <br /> 2.1 front-end - React
       <br /> 2.2 backend - NodeJS
    <br /> 3. App : Java
<br /> **Tentative Workflow/Timeline**:
    <br /> 1 Web: 4-5 weeks
    <br /> 2 ML: 2-3 weeks for building data, next 2-3 weeks for training the model.

2. #### Diagnosing of Diseases using Medical Imaging

**Project Title**: Web and App platform for fast and effective diagnosis of critical diseases using medical imaging <br />
**Proposed by**:  Rishabh Tiwari (ML), Nainesh Hulke(ML), Rishabh Agarwal (Server & AppD), Ridhish Jain (WebD & Server) <br />
**Required divisions(ML/Web/AppD/security)**: ML, Web, AppD <br />
**Details**: <br />
    **Description**: <br /> 
    Our project aims to  provide support for medical diagnosis, especially for rural areas and also to cope up with the problem of shortage of medical experts.The idea is to design and train various deep learning architecture for predicting the severity of following diseases 
<br /> **Link to similar work(if any)**: <br /> 
**Major Tech stacks/skills required (tentative)**:  Flask, Node JS express, VS code, React, Android Studio, Github, Pytorch,  Fastai. <br />
**Tentative workflow/ Timeline** <br />
    Week 1 : Research and Study <br />
    Week 2 : Basic Layout <br />
    Week 3 : Web - ML integration <br />
    Week 4 : Web - ML - App integration <br />

3. #### Krishi App for Farmers 

**Project Title**: Krishi App for farmers. <br />
**Proposed by**:  MOHIT MUDE(appD) <br />
**Required divisions(ML/Web/AppD/security)**:AppD,ML <br />
**Details**: <br />
    **Description**: <br />
    Nowadays,what happens in our country is that a farmer has no access to the current price rates of a crop.Also he is not informed about the goverment schemes for his betterment.for selling his produce a farmer moves to a nearby mandi if the prices are lower at that time he/she is left with no option other than to sell his production at a lower cost to the middlemans which later will get a huge chunk of profit by reselling the crop at the right place and right time.
    <br /> What our app will do is that,we would provide a platform where framers can create their own community and discuss their issues on a single platform.Also oru App will implement ML in forecasting future weather conditions and crop prices in the market by analysing varying data sets from different governmental agencies.This will help the farmers to know when to sow which seeds for better production.
    <br /> Also ,our app will provide a platform for online selling and buying of crop and this will reduce the role of middleman indulged in this business. 

**Link to similar work**:SIH 2019 problem statement(agriculture) <br />
**Major Tech stacks/skills required (tentative)**: <br />
    1. Appd: Android Studio <br />
    2. ML:for weather forecast and price analysis of crops day/monthwise (algorithm to be decided) <br />
**Tentative workflow/ Timeline**: 4 Weeks; 

4. #### Home Automation System

**Project title**: Home automation system <br />
**Proposed by**: Madhav Shah sir, Nikhil Arora sir, Mamoon, Rahul. <br />
**Required divisions**: Hardware/ web/app <br />
**Details**: <br />
    **Description**: <br /> 
    The project aims at developing an innovative system which can control household appliances based on user inputs in the app, with the help of Raspberry pi along with other necessary sensors and actuators. <br />

**Link to similar work(if any)**: <br />
**Major Tech stacks/skills required**: Raspberry PI, dht11 , gas detecting sensor, ldr. <br />
**Tentative workflow/ Timeline**: To Be Decided <br />

5. #### Campus Selection System 

**Project Title**:Campus selection system <br />
**Proposed by**: Naman Zelawat <br />
**Required divisions(ML/Web/AppD/security)**:ML, Webd. <br />
**Details**: <br />
	A virtual experience of companies selection rounds like coding, HR etc based on  
	the previous or past year interviews.
	Decreasing and increasing the level of questions accordingly.
	
**Link to  similar work(if any)**: <br />
**Major Tech skills required**: <br />
    1. Any frontend framework or library(angular or react) <br />
    2. Backend with node.js(express) or go(beego(first try)) <br />
    3. ML(part to be proposed later) <br />

6. #### IIT(ISM) Library Search 

**Project Title**: IIT(ISM) Library Search <br />
**Proposed by**: Nikhil BN <br />
**Required divisions** : Web, AppD <br />
**Details**: <br />
    **Description**: <br /> 
    Search for books that are available in the library online without visiting the library.
<br /> **Link to similar work(if any)**: <br />
**Major Tech stacks/skills required (tentative)**: <br /> 
    1. Web App (Frontend: React JS, Backend: Node JS), <br />
    2. Android App(Java or React Native) <br />
**Tentative workflow/ Timeline**: 4 weeks for Web and 3 weeks for App 

7. #### Timelining

**Project Title**:Timelining <br />
**Proposed by**: AAYUSH NARWAY(APPD) <br />
**Required divisions(ML/Web/AppD/security)**:APPD,WEBD,ML <br />
**Details**: <br />
    **Description**: <br />
    The idea is to create a better event managing system. Word timeline refers to a type of linear calendar on which events are marked.
    There will be multiple timelines which one can view. <br />
    Each identity will have its own timeline - public and personal. Every user can enroll to others timeline. Personal timeline is for personal use and public timeline is for others to view.
    One will post events on public and personal timeline.<br />
    Lets say a club post an event on its public timeline now people can react to that as interested, not interested, going , not going. Thus the one who posted the event will get stats of how many people may come.
    <br />Going user will get this event moved to their personal timeline.<br />
    Similarly class timeline will be controlled by the class CR.
    While posting the event we will get advice from the system as what is the best time to schedule a event. This would be made possible using ML. It will go through the personal timelines of everyone who has enrolled on the timeline of the club.
    After or during the event one can also post live videos of the event, Images related to the event can be posted.
    This will make easy to schedule meetings,events, fests. Easy promotions. Easy anticipation.

**Link to similar work(if any)**: <br />
**Major Tech stacks/skills required (tentative)**: <br /> 
    1. app:android studio, github <br />
    2. Backend: nodeJs <br />
**Tentative workflow/ Timeline**: To be decided <br />

**Link to other project proposals**: https://docs.google.com/document/d/11HQmhwmsGTQQWo2sYCd0Nw8dhH-ORt1VfsEIz4loTRs/edit?usp=drivesdk

### The Projects which were kept on hold are: 

1. Neural Style Transfer on Videos
2. Garbage Collecting Bot

### Conclusion

1. Detailed Proposals to be given for the projects that are selected, along with the number of people required from each division for the project.

2. Assignment of the projects will be done after the detailed proposals are given.

3. Member Participation in various workshops held by Cyberlabs was monitored. 

## Agenda for the next session

Next session will be held on 01/10/2019, Tuesday. Updates about work ongoing in CyberLabs will be discussed. Member Participation of the Club will also be monitored.

## Credits

*Report Compiled by*: Saloni Mohta

*Absentees*:

* Rishabh Verma
* Aayush Ahuja

1. Machine Learning :

    3rd Years:

    * Ali
    * Shivansh
    * Anshuman
    * Mihit
    * Nirav
    * GK
    * Osama

    2nd Years:

    * Ali

2. Android :

    3rd Years:

    * Shridhar
    * Vanshika
    * Tazril
    * Aman
    * Perul

    2nd Years:

    * Ankit
    * Sanket

3. Cyber Security:

    2nd Years:
        
    * Akshat
    * Satya
    
4. Web :

    3rd Years:

    * Prateek
    * Gaurav
    * Ujjwal
    * Anushka
    * Kirti
    * Anurag
    * Sanyam

5. Graphic Designing:
    
    * Nitish
    * Ashutosh














