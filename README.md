# Store and Customer
These HTML pages consist of two sections Store and Customer. In store page we have parent and child categories,it shows list of portfolios according to category and there is search bar on top where customer can search portfolio. In store design, on left side we have categories and sub categories and on right side we have list of portfolio under the selected category. Customer section is restricted with Login Authentication. If customer comes through invitation link then he don't need to login to view the invitation portfolio but if customer try to see other portfolio except the invitation or try to search, then it will prompt customer to login first.

# Connect Store and Customer with API

We have created an API which will help for front end developer to dynamically change section of store and customer pages. Description of API [Store and Customer](https://app.swaggerhub.com/apis/Dev007/docketapi/1.1)

### Connect Store Section with API

###### Basic

To call any URL in API we need Authentication token. To get valid authentication we will use this (Auth URL)[https://app.synpat.com/v1/auth] and use POST method and pass key parameter and value of the key parameter is given in the description. API will validate key and in return it will generate valid token, which will help us to call any other method in the API. For the (Login) [https://app.synpat.com/v1/login] and use POST method and send email and password parameter, API will validate and and in return it will generate valid token, replace this valid token with old token if it was generated previously, so that if you call any data for customer section you will get valid data otherwise it will prompt you invalid token.

###### Parent Category

To get data for the category we will call [https://app.synpat.com/v1/category] and pass valid token in the Authentication headers, In return we will get the data for parent category list. show category with anchor tag

###### Child Category

To get data for the child category we will call [https://app.synpat.com/v1/category/parent_category] . We will pass the parent category ID and also pass valid token in the Authentication headers, In return we will get the data for child category list. Show as only text not click able.

###### Portfolio list or Invitation portfolio:
To get data for the list of portfolios under specific category or for the invitation portfolio call to [https://app.synpat.com/v1/portfolio/{category}/{invitation}]
If customer comes with invitation link then in the invitation there will be invitation number of portfolio or if customer want to see portfolio for other categories than in that case pass invitation parameter with 0. 

###### Search portfolio:
To search from all portfolio call to [https://app.synpat.com/v1/search] and pass two parameter "q" and "order_by".  


### Connect Customer Section with API
In customer section on left side we have few link like Dashboard, My Account, My Transaction, My Wishlist, My Preferences, My Membership, Continue Shopping
	
###### Basic
Only authenticated customer can enter in this section. So make sure you generate a valid token with customer email and password

###### Dashboard
In dashboard we are showing summary of customer information like Company Info, User list, wish list list, preference list. All have different method to get the information. In dashboard these information is just to display only, customer cannot perform any action on these section. 
- For getting company Info call [https://app.synpat.com/v1/company_info]
- For getting user list call [https://app.synpat.com/v1/company_users_list]
- For getting wish list call [https://app.synpat.com/v1/customer_wishlist]
- For getting preference list call [https://app.synpat.com/v1/customer_preferences]

###### My Account
Under this customer can edit company information, can add or update bank details, can add or delete users and can update password.
- For getting company Info call [https://app.synpat.com/v1/company_info]
- For getting user list call [https://app.synpat.com/v1/company_users_list]
- For updating information or add user call [https://app.synpat.com/v1/customer_account]
- For remove user call [https://app.synpat.com/v1/remove_user]

###### My Transaction
Under this section customer can see list of Licenses which already bought, can see list of deals , and there is search option where customer can enter the Portfolio number and will see list of buttons like View Agreement, Check Availability, Customize License, Download agreement or upload agreement. 

- For getting list of licenses call [https://app.synpat.com/v1/customer_transactions]
- For getting list of deals call [https://app.synpat.com/v1/customer_deal_flow]
- For getting Portfolio info call [https://app.synpat.com/v1/portfolio_info/{portfolio_number}]
- For check availability call [https://app.synpat.com/v1/check_availability/{portfolio_number}]
- For download call [https://app.synpat.com/v1/download/{portfolio_number}]
- For customize call [https://app.synpat.com/v1/customize/{portfolio_number}]
- For request to participate call [https://app.synpat.com/v1/participate/{portfolio_number}]
- For uploading document call [https://app.synpat.com/v1/upload/{portfolio_number}]

###### My Whishlist
Under this section customer can see list of portfolio that selected for wishlist from the store section, here customer can delete any portfolio from wishlist.

- For getting wish list call [https://app.synpat.com/v1/customer_wishlist]
- For deleting portfolio from wishlist call [https://app.synpat.com/v1/delete_portfolio_customer_wishlist]

###### My Preference
Under this section customer can see list of preference.

- For getting main category list call [https://app.synpat.com/v1/category]
- For getting child category list call [https://app.synpat.com/v1/category/parent_category]
- For getting preference list call [https://app.synpat.com/v1/customer_preferences]
- For updating preference call [https://app.synpat.com/v1/customer_update_preferences]

###### Continue Shopping
This will redirect customer to back to the store page




