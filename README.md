# Introduction 

The intent of this project prosposal is to layout the problem policy makers and university administrators will face due to the Covid-19 pandemic. 

Currently, universities across the United States are faced with a serious predicament. Many are at the crossroads of deciding whether to re-open their campuses for the upcoming fall semester; is the ongoing COVID-19 pandemic too significant of a barrier to overcome, or is there a way to bring students back safely? 

We collaborated on a project called covID@Cal, and presented at the Jacobs Institute for Design Innovation at UC Berkeley, as a part of their Spring COVID-19 project showcase. In this proposal, we received mentorship and assistance from Jacob’s staff, which led us to fully develop our idea.

With our idea, every student’s individual “covID” will function as the tracking step in the process of contact tracing. Every time a student walks into any building on campus, and possibly stores in the surrounding areas as well, they will scan their covID (generated on our mobile app) on a sensor at the door. Every time a student enters a building, this information is sent to a secure database that will hold data regarding who has entered a specific building at a given time. This data will remain anonymous, until an individual tests positive for COVID-19 at the Tang Center, where testing will be readily available in the fall.

# Scientific Context

<< Talk about how covid spreads, mortality, underlying conditions>>

<< Put graphs and images>>


# What is covID@Cal

<< Insert from medium article/presentation>>
<< Put an image of a phone with QR Code>>

## Understanding covId@Cal

# Use Cases



## Primary Use Cases

## Secondary Use Cases


# Systems Design

<< Discuss the 4 system components and the high level diagram>>

## 1.  Encoder App

### Objective 
The git hub repo (github.com/rishabh-parekh/covid-encoder.git) has the sample code of taking in User data and encoding it in a QR/Barcode. 

### Code Snippet
```
<QRCode
            level="Q"
            style={{ width: 256 }}
            value={JSON.stringify({
              static_data: {
                id: 928328,
                name: "Rishabh Parekh",
                dob: "05/16/2000",
                address: "Berkeley",
                chronic_conditions: {
                  conditions: ["Asthma"]
                }
              },
              dynamic_data: {
                fever: false,
                temperature: 97,
                blood_pressure: 60,
                pulse: 80
              }
            })}

```

### Workflow

The user will generate the QR code on the covId App, and update it every day based on new conditions - temperature, heart rates.  (Press the Generate QR Code button)

The user will use the QR Code to get entry in various university locations

### Data 

Discuss the parts for the data , static, dynamic data, health data. 

This would be from the presentation. 


## 2. Scanner App

### Objective 
The git hub repo (github.com/rishabh-parekh/covid-scanner.git) has the sample code of scanning the QR Code (without the personal data), Location information and posting it to the API Server

### Code Snippet
```
{
  location : "Wheeler Hall",
  date : ""
  time : ""
  user : {
              static_data: {
                address: "Berkeley",
                chronic_conditions: {
                  conditions: ["Asthma"]
                }
              },
              dynamic_data: {
                fever: false,
                temperature: 97,
                blood_pressure: 60,
                pulse: 80
             }
       }
   }   
}|

```


Scanner Code snippet 

```
QRScanner.initiate({
        match: /^[a-zA-Z0-9]{16,18}$/, // optional
        onResult: function (result) { axios.send('DONE: ', result); },
        onError: function (err) { console.error('ERR :::: ', err); }, // optional
        onTimeout: function () { console.warn('TIMEOUT'); } // optional
    })
```

### Workflow

The scanner similar to TSA scanner, will scan the QR code, anonmyise it and add location and time, and post it to the API Server. 

## Data Privacy
In regards to data privacy, the data would be anonymized and stripped off any personal data (ie. name, address, phone number, student ID, date of birth).
The data would be posted to an API server in an encrypted format. 
### Data 

Discuss the parts for the data , static, dynamic data, health data. 



## 3. API Server

### Objective 
The objective of the API Server is to get all the covid user data posted, and provide API's for making decisions. 


### Code Snippet
```
GGET    /users
GET    /locations/1
POST   /user


GET /?title=json-server&author=typicode
GET /posts?id=1&id=2
GET /comments?author.name=typicode
```


API Server Code snippet 
(https://github.com/typicode/json-server)
```

```

### Workflow

 

### Data 


## 4. Data Analytics

### Objective 
The objective of the data analytics is to provide administraton and policy makers the contextual data to make decisions. 

## Prediction Data

Over here, we will reference the Reich lab and other fanstic data collectors and predictors. Our specific goal to to enable universities and policy makers to contextualize data along with prediction models....

### Code

< Example jypter notebook to read json data and make bars/charts>



## Notifications

This is to emplain how to communications would work between Tang and students

Exposure notifications from Apple and Google

County level notifications


# University Policy Decisions

<Section on what policy decisions universities have to make>

<< Use the emails from campus, various subcommittee >>

1. Capacity of classrooms

Large lecture halls, smaller sections, labs, 

2. Common Areas: cafeterias, libraries, 

3. 

## Policy Challenges:

## Data Requirements: 

What kind of data they need to support their policy decision making?

How can the data from this app (approach) help them?


## Where else can this be used: 

- Sports events
- Airports
- Music concert



# Authors
  
  Rishabh Parekh (@rishabh-parekh) ![rishabh](images/rishabh.png)

  Spencer Le () ![rishabh](images/rishabh.png)

  Michael Savides () ![rishabh](images/rishabh.png)
