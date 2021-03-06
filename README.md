# An API built to show off hapi.js

This web API was built to demonstrate some of the [hapi](hapijs.com) features and functionality. It was part of a talk given at [Asyncjs](http://asyncjs.com/be-more-hapi/) on the 10 October 2013. 

The API is a simple calculator that allows you to add, subtract, divide or multiple two numbers. To demonstrate a more common set of API calls I also added methods to store sums into a mongodb database. 


## Install
You first need to install [node.js](http://nodejs.org/) and [mongodb](http://www.mongodb.org/downloads) if you do not already have them on your computer. Then download the code from github: 

    $ git clone https://github.com/glennjones/be-more-hapi.git

or

    $ curl -L https://github.com/glennjones/be-more-hapi/tarball/master | tar zx
   
    
    
## Run

1. Move into the project directory `$ cd be-more-hapi`
2. Run `$ npm install`
3. Start the mongodb server `$ mongod`
4. Run `$ node bin/be-more-hapi`
5. Connect to the server using `http://localhost:8000`


## Sums
All the sum endpoints are http GET requests. Where the two numbers are the last two fragments of the URL:

    http://localhost:8000/sum/multiple/5/6
    
If the sum is completed without error the response is also a simple format:

    {
        "equals": 30
    }


## Errors

The error format always has 3 properties; code, error and message. There is an optional fourth property validation which is added if the input is in the incorrect format. 
    
    {
      	"code": 400,
  		"error": "Bad Request",
  		"message": "the value of b must be a number",
  		"validation": {
    		"source": "path",
    		"keys": [
      		"b"
    		]
  		}
	}



## Mocha integration test
The project has example integration and unit tests. To run the test within the project type the following command

    $ mocha --reporter list




