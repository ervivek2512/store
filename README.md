# Store and Customer
These html pages consist of two sections Store and Customer. In store page we have parent and child categories,it shows list of portfolios according to category and there is search bar on top where customer can search portolfio. In store design, on left side we have categories and sub categories and on right side we have list of portfolio under the selected category. Customer section is restricted with Login Authentication. If customer comes through invitation link then he don't need to login to view the invitation portfolio but if customer try to see other portfolio except the invitation or try to search, then it will prompt customer to login first.

# Connect Store and Customer with API

We have created an API which will help for front end developer to dynamically change section of store and customer pages. Description of API [Store and Customer](https://app.swaggerhub.com/apis/Dev007/docketapi/1.1)

### Connect Store with API

	###### Basic
	
	To call any url in API we need Authentication token. To get valid authentication we will use this (Auth url)[https://app.synpat.com/v1/auth] and use method POST and pass key parameter and value of the key parameter is given in the description. API will validate key and in return it will generate valid token, which will help us to call any other method in the API
	
	###### Parent Category
	
	To get data for the category we will call [https://app.synpat.com/v1/category] and pass valid token in the Authentication headers, In return we will get the data for parent category list. show category with anchor tag
	
	###### Child Category
	
	To get data for the child category we will call [https://app.synpat.com/v1/category/parent_category] . We will pass the parent category ID and also pass valid token in the Authentication headers, In return we will get the data for child category list. Show as only text not click able.
	
	###### Portfolio list or Invitation portfolio:
	To get data for the list of portfolios under specific category or for the inviation portfolio call to [https://app.synpat.com/v1/portfolio/{category}/{invitation}]
	If customer comes with invitation link then in the inviation there will be inviation number of portfolio or if customer want to see portfolio for other categories than in that case pass inviation parameter with 0. 
	
	






