# Store and Customer
These html pages consist of two sections Store and Customer. In store page on left side we have categories and sub categories and on right side we have list of portfolio under the selected category. Customer section is restricted with Login Authentication. For the store if user is coming with the invitation link then he don't need to login but user coming to store without invitation then customer has to login first.

# Connect with API
We have created an API which will help us to dynamically change section of store and customer pages. Description of API [Store and Customer](https://app.swaggerhub.com/apis/Dev007/docketapi/1.1)

### Connect Store with API
	#### Basic
	To call any url in API we need Authentication token. To get valid authentication we will use this (Auth url)[https://app.synpat.com/v1/auth] and use method POST and pass key parameter and value of the key parameter is given in the description. API will validate key and in return it will generate valid token, which will help us to call any other method in the API
	
	#### Parent Category
	To get data for the category we will call [https://app.synpat.com/v1/category] and pass valid token in the Authentication headers, In return we will get the data for parent category list.
	
	#### Child Category
	To get data for the child category we will call [https://app.synpat.com/v1/category/parent_category] . We will pass the parent category ID and also pass valid token in the Authentication headers, In return we will get the data for child category list.
	
	#### Portfolio list or Invitation portfolio
	






