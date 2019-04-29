# Driver and Car Management Continued.
So far we have one `model` the `company` model but this may not be sufficient enough for our application

## Your Mission
Lets break our app into more models and pass references.

## Your Task

Let's keep track of our Restful Routes as we build out our app. Copy/paste this table into a fresh file, open an excel/sheets spreadsheet or draw on a piece of paper. Feel free to add more columns and notes to help you put it all together.

Index, New and Create has been completed for you.

#### Restful Routes
|#|Action|URL|HTTP Verb|EJS view filename|mongoose method|
|:---:|:---:|:---:|:---:|:---:|:---:|
|1| Index | /companys/ | GET | index.ejs | Company.find()|
|2| Show |||||
|3| New | /companys/new | GET | new.ejs | none |
|4| Create | /companys/ | POS T| none | Company.create(req.body)|
|5| Edit |||||
|6| Update |||||
|7| Destroy ||||||


|#|Action|URL|HTTP Verb|EJS view filename|mongoose method|
|:---:|:---:|:---:|:---:|:---:|:---:|
|1| Index | /cars/ | GET | index.ejs | Car.find()|
|2| Show |||||
|3| New | /cars/new | GET | new.ejs | none |
|4| Create | /cars/ | POST| none | Car.create(req.body)|
|5| Edit |||||
|6| Update |||||
|7| Destroy ||||||


|#|Action|URL|HTTP Verb|EJS view filename|mongoose method|
|:---:|:---:|:---:|:---:|:---:|:---:|
|1| Index | /drivers/ | GET | index.ejs | Driver.find()|
|2| Show |||||
|3| New | /drivers/new | GET | new.ejs | none |
|4| Create | /drivers/ | POS T| none | Driver.create(req.body)|
|5| Edit |||||
|6| Update |||||
|7| Destroy ||||||


## Step 1
 1. Create one model each for `Car` and `Driver` with the data embedded in :cars and :drivers
 1. Think about this, One `Company` *can have many* `Cars` and `Drivers`
 1. One `Driver` *can driver many* `Cars`

## Step 2
 - Create 
