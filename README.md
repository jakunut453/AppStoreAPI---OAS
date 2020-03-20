# AppStoreAPI-OAS
An OAS 3.0 specification for an api made for any software application store

An API specification was made for a Mobile App store using OAS 3.0 (Open API Specification). The api specification was made on Swaggerhub following the OAS 3.0 guidelines. This a generic API that can be made use in many applications. It could be used in the Mobile Application store for phones Ex:AppStore for IOS, PlayStore for Android. Or it can be extended for even desktop application stores such as the windows store used by microsoft. The data is broken down into collections such as apps, users and developer. Endpoints are described to manipulate the data using appropriate GET,PUT,POST and DELETE calls. In addition it has a featured collection that has dynamic data for things like top charts which may change daily.

## To view the documentation

* [Documentaion using swagger](https://app.swaggerhub.com/apis-docs/jakunut453/Mobile_AppStore_API/2.0.0#/)
* [YAML OAS3 on swaggerhub here](https://app.swaggerhub.com/apis/jakunut453/Mobile_AppStore_API/2.0.0#/App)

You can view it directly [Here](https://app.swaggerhub.com/apis-docs/jakunut453/Mobile_AppStore_API/2.0.0#/). This is a mockup of what it is supposed to look like and was generated using Swagger.
![documentation](https://github.com/jakunut453/AppStoreAPI-OAS/blob/master/screenshots/documentation.PNG)


To view the YAML code you can see it on SwaggerHub [Here](https://app.swaggerhub.com/apis/jakunut453/Mobile_AppStore_API/2.0.0#/App)
![code](https://github.com/jakunut453/AppStoreAPI-OAS/blob/master/screenshots/code.PNG)
## Features

Below are some of the features of the API
* Oauth2 authentication for requests with different scopes for each of them.
* Made good use of components to reduce the size of code.
* Each request has appropriate error codes

## Endpoints

### App
The endpoints are to manipulate the app data.
Endpoints | Request Methods | Description
------------ | ------------- | ------------- 
/apps | GET, POST | List of apps
/apps/{appId} | GET, POST, PUT, DELETE | A particular app
/apps/{appId}/versions | GET, POST | All versions of an app
/apps/{appId}/versions/history | GET | The change history
/apps/{appId}/versions/{versionNumber} | GET | A particular version
/apps/{appId}/reviews | GET | Review details
/apps/{appId}/screenshots | GET, post, delete | screenshots of an app

### Categories
Endpoints to manipulate categories. The categories can change over time and have GET request to accomodate the changing data.
Endpoints | Request Methods | Description
------------ | ------------- | ------------- 
/categories | GET, POST, PATCH, DELETE | Availabe categories
/categories/{categoryName} | GET | Apps under a category

### Developers
All information on the publishers of Apps
Endpoints | Request Methods | Description
------------ | ------------- | ------------- 
/developers | GET, POST | Details on all developers
/developers/{id} | GET, POST, PULL, DELETE | Specific developer
/developers/{id}/apps | GET, PATCH | Developer's apps
/developers/{id}/apps/{appId} | GET | Specific app of a dev

### Users
To get information on the users.
Endpoints | Request Methods | Description
------------ | ------------- | ------------- 
/users | GET, POST | all users
/users/{id} | GET, POST, PULL, DELETE | specific user
/users/{id}/apps | GET, POST, PATCH, DELETE | user's apps
/users/{id}/recomendations | GET | recommendation to a user
/users/{id}/wishlist | GET, POST, PATCH, DELETE | the user's wishlist

### featured
The featured endpoints are interesting. They handle dynamically data that changes frequently. For example top charts of the entire app store change often and this endpoint is used to query that data. Heuristic are used to get other sort of data such as the currently trending apps, etc. 
Endpoints | Request Methods | Description
------------ | ------------- | ------------- 
/featured/top-charts | GET | Get the apps in the current top charts.
/featured/{heuristic} | GET | Get a ranking of apps based on some rule( Most downloads, rating)
