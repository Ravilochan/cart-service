# cart-service
This is Service which enables User's to add Ideas and store them in cart. To Checkout & but that Idea. This is just a phase before paying/buying for an Idea. 
A User can add an available IDea to the cart and proceed to Checkout.

# Installation
Clone this repository into your local 

```bash
git clone https://github.com/Ravilochan/cart-service.git
```
Go to that directory
```bash
cd <directory-name>
```
Install all Dependencies for Node to run . You need to have Node , npm already installed in your computer to run this command

```bash
npm install
```
# Run Service

To Run this service your system or Local should have NodeJS Installed.
This starts the service on http://localhost:7000 on your computer 
```bash
npm start
```
or you can Start this service by command :

```bash
node api/index
```

# Usage
This Service has API endpoints at 
```bash
/api/cart --> PUT Request

/api/uncart --> PUT Request

/api/cart/:id --> GET Request
```
For /api/fav - POST Request
Data sending to Request in body should be like 
```JSON
{ 
"user":
     {
     "_id":"5d6ede6a0ba62570afcedd3b"
     },
"cart":
     {
     "_id":"5d6ede6a0ba62570afcedd32",
     "idea_owner": "String",
     "idea_owner_name": "String2",
     "idea_genre": "String3",
     "idea_headline": "String idea_name",
     "idea_description": "String idea_description",
     "price": 50
     } 
}
```
Here the _id in user is the MongoDB UID / _id unique for every user. This shoud 12 characters and uinque and accoridng to the rules of MongoDB _id.
Here the _id in cart is the MongoDB UID / _id unique for every Idea. This shoud 12 characters and uinque and accoridng to the rules of MongoDB _id.
For adding an IDea to the cart - PUT Request:
The user needs to send User detalis in "user" and Idea Details in "cart"

Response :
```JSON
{
    "cart": [
        "5d6ede6a0ba62570afcedd32"
    ],
    "_id": "5d6ede6a0ba62570afcedd3b",
    "__v": 0
}
```

For /api/uncart - PUT Request
PUT data in Body of Request should be like 
```JSON
{ 
"user":
     {
     "_id":"5d6ede6a0ba62570afcedd3b"
     },
"cart":
     {
     "_id":"5d6ede6a0ba62570afcedd32"
     } 
}
```
Here the _id in user is the MongoDB UID / _id unique for every user. This shoud 12 characters and uinque and accoridng to the rules of MongoDB _id.
Here the _id in cart is the MongoDB UID / _id unique for every Idea. This shoud 12 characters and uinque and accoridng to the rules of MongoDB _id.
For making this PUT un-cart Request ( un-cart an Idea ) :
The user needs to send User detalis in "user" and only Idea _id in "cart"
Response :
```JSON
{
    "cart": [],
    "_id": "5d6ede6a0ba62570afcedd3b",
    "__v": 0
}
```
To Get all cart ideas of a User :
/api/cart/:id -> GET Request
 here Params :id is the User's UID/_id from User collection. 
 Here the _id in user is the MongoDB UID / _id unique for every user. This shoud 12 characters and uinque and accoridng to the rules of MongoDB _id.
 
 Response :
 ```JSON
 [
    {
        "_id": "5d6ede6a0ba62570afcedd38",
        "idea_owner": "String",
        "idea_owner_name": "String2",
        "idea_genre": "String3",
        "idea_headline": "String idea_name",
        "idea_description": "String idea_description",
        "price": 50
    },
    {
        "_id": "5d6ede6a0ba62570afcedd39",
        "idea_owner": "String",
        "idea_owner_name": "String2",
        "idea_genre": "String3",
        "idea_headline": "String idea_name",
        "idea_description": "String idea_description",
        "price": 50
    }
]
```
 
 
