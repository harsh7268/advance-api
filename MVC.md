# NodeJS,Mongoose,Express Project in MVC Architecture

**Supported version of nodejs >= 12**,
**Supported version of mongoose >= 6**

## About 
- This is a Node application, developed using MVC pattern with Node.js, ExpressJS, and Mongoose. 
- MongoDB database is used for data storage, with object modeling provided by Mongoose.

## Initial
1. Install all dependency
```$ npm install```
2. Start production server
```$ npm run start```
2. Start development server
```$ npm run dev```
4. Credentials
	- One user with User role,
	# Default User credentials
	**username** : Deshaun_Stamm@hotmail.com
	**password** : FfylhhlAanYnOR1

	- One user with Admin role,
	# Default Admin credentials
	**username** : Josefina90@gmail.com
	**password** : 8fw_WjOL8D29Oez


## How to use generated APIs:
[Click here to visit documentation](<https://docs.dhiwise.com/docs/node/generate-apis/> "API Documentation")


## Folder structure:
```
  ├── app.js       - starting point of the application
  ├── config
  │   └── db.js    - contains api database connection
  ├── constants    - contains commonly used constants 
  ├── controllers               
  │   └── platform - contains business logic
  ├── jobs         - cron jobs
  ├── models       - models of application
  ├── middleware   - middleware of application like role,authentication,device permisions etc.
  ├── postman      - postman collection files
  ├── public       - public folder store all static files like image,css,js etc.
  ├── routes       - contains all the routes of application
  ├── services     - contains commonly used services
  ├── seeders      - contains all seeders means default user createed
  ├── socket       - Socket contain all events
  ├── __test__     - __test__ folder contain all testing logic using jest/mocha library
  ├── utils        - contains utility functions
  └── views        - templates
```


## Detail Description of Files and folders

1. app.js
- entry point of application.

2. config
- Config files that contains configration files like database connections, authentication strategy  etc.
```
	├── config
		├── db.js                                - contains database conection
        ├── passport
			├── adminPassportStrategy.js          - admin authenctication strategy usign JWT token
            └── userPassportStrategy.js           - user authenctication strategy usign JWT token
        ├── firebase
			├── auth.js.js                        - authentication of token
            ├── firebase.js                       - Initiate firebase-admin with firebase configration
            └── serviceAccount.json               - contains all firebase scretes key and id's
```

3. constants
- constants used across application.

4. controllers
- Controller files that contains Business logic
```
	├── controller
		├── platform                          - platform is name applications like user,hub,admin etc.
            └── version                       - version is number which you release for buisness
			      └── modelNameController.js  - contains CRUD Operations
```

5. jobs
- Cron jobs (means you create a logic and execute in certain time period automatically)
```
	├── jobs
		├── index.js                         - root file of jobs import all jobs
        ├── createUser.js                    - create user automatically in certain time
        └── paymentChecker.js                - check payment in certain time
```

6. middleware
- Middleware files for authentication, authorization and role-access.
```
	├── middleware
		├── auth.js                         - check user authentication
        ├── checkRolePermision.js           - check user role
        └── googlePassportStrategy.js       - social login authentication by passport.js
```

7. models
- Database models 
```
	├── models
		└── modelName.js                         - Define database model,methods etc.
```

8. postman
- Postman collection of APIs (Import this JSON in Postman to run the APIs)

9. public
- - Assets used in application (Public folder contains all static files and images etc.)
```
	├── public
		├── css                         - All Css files define here
        ├── js                          - All js files define here
        ├── images                      - All Images Store here
```

10. routes
- index.js file, exports platform routes, imported into app.js to access all the routes.
```
	├── routes
		├── platform                     - platform is name applications like user,hub,admin etc.
            └── version                  - version is number which you release for buisness
			    ├── modelNameRoutes.js   - contains CRUD operation routes
			    └── index.js             - exports model Routes
		└── index.js                     - exports platform routes

```

11. services
- Services folder contain all type of service which used in application like notification,payment,email,sms,whatsapp etc.
```
	├── services
		├── notifications    
            └── index.js                    
        ├── payments  
            ├── instamojo.js
            ├── phonepay.js
            ├── paytm.js
            ├── razorpay.js
            └── crypto.js
        ├── pushNotifications 
            ├── awssns
                └── index.js 
            ├── google
                └── index.js 
            ├── firebase  
                └── index.js
        ├── email   
            ├── sendgrid.js
            ├── nodemailer.js
            ├── awsses.js
            └── sendinblue.js
        ├── sms  
            ├── fasttosms.js 
            ├── msg91.js
            └── twilio.js
        ├── whatsapp.js
        ├── slack.js
        └── fblead.js

```

12. seeders
- Seeders containe to make by default created in database for testing like - users , admin etc.
```
	├── seeders
	    └── index.js        
```

13. socket
- Socket folder contain all socket events and handelere used in application
```
	├── socket
        ├── handler.js
	    └── event.js        
```

14. test
- Test folder is used for testing of application using jest,mocha etc. library
```
	├── __test__
          └── platform
              └── version   
                  ├── auth.test.js
                  ├── payment.test.js  
                		                          
```

15. utils
```
	├── utils
        ├── response                 - response send by request
            ├── responseCode.js
            ├── responseStatus.js
            ├── responseHandeler.js 
            └── index.js
		├── validations              - joi/yum validations files for every model
            ├── userValidation.js
            ├── paymentValidation.js
        ├── common
            └── common.js            - Here all common functions create in whole application
		├── dbService.js             - Database functions 
        ├── deleteDependent.js       - delete data automatically 
		└── validateRequest.js       - validate request based on model schema

```

16. views
-  Views Folder contain all template files whose see in frontend
```
	├── views
        ├── email                
            ├── changePassword.ejs
            ├── register.ejs
            └── login.ejs
        ├── sms                
            ├── changePassword.ejs
            ├── register.ejs
            └── login.ejs
        ├── payment                
            ├── success.ejs
            ├── pending.ejs
            └── failed.ejs
        └── index.ejs

```

17. env files
- You can add credentials and port, database values as per your environment(Development/Production).
- If you are running test environment then test cases will run using test database,and its configuration is there inside app.js