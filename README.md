<h1 align="center">ExpressJS - Simple Online Payment and Transaction RESTfull API</h1>



Zwallet is an application that provides you with online payment and transaction services for backend only. Built with NodeJs using the ExpressJs Framework.
Express.js is a web application framework for Node.js. [More about Express](https://en.wikipedia.org/wiki/Express.js)

## Requirements
1. <a href="https://nodejs.org/en/download/">Node Js</a>
2. Node_modules
3. <a href="https://www.getpostman.com/">Postman</a>
4. Web Server (ex. localhost)

## How to run the app ?
1. Open app's directory in CMD or Terminal
2. Type `npm install`
3. Make new file a called **.env**, set up first [here](#set-up-env-file)
4. Turn on Web Server and MySQL can using Third-party tool like xampp, etc.
5. Create a database with the name z-wallet, and Import file to **phpmyadmin**
6. Open Postman desktop application or Chrome web app extension that has installed before
7. Choose HTTP Method and enter request url.(ex. localhost:8080/)
8. You can see all the end point [here](#end-point)

## Set up .env file
Open .env file on your favorite code editor, and copy paste this code below :
```
ACCESS_TOKEN_SECRET = 'E-wallet&&^#&(!#*('

APP_URL =http://localhost:8080/

DB_NAME = z-wallet
DB_USER = root
DB_PASS = 
DB_HOST = localhost
```

## End Point

**1. ADMIN**

A. Login
* `/admin/login`(POST)
  * `{"email": admin@gmail.com, "password": 123}`

B. Show user(GET)
* `/admin/listMember`
  * `input (token from login) to Authorization with type bearer token`

C. Show Profile admin(GET)
* `/admin/profile`
  * `input (token from login) to Authorization with type bearer token`

D. Create User(POST)
* `/admin/createMember`
  * `input (token from login) to Authorization with type bearer token`
  * `{"username": beta, "firstname": beta, "lastname": tester, "email": beta@mail.com, "password": 123, "pin": 123456, "phone": 08333444}`

E. Edit User(PATCH)
* `/admin/updateMember/:id`
  * `input (token from login) to Authorization with type bearer token`
  * `{"username": beta, "firstname": beta, "lastname": tester, "email": beta@mail.com, "password": 123, "pin": 123456, "phone": 08333444}`

F. Edit Profile Admin(PATCH)
* `/admin/profile/update`
  * `input (token from login) to Authorization with type bearer token`
  * `{"firstname": beta, "lastname": tester, "email": beta@mail.com, "password": 123, "pin": 123456, "phone": 08333444}`

G. Delete User(DELETE)
* `/admin/deleteMember/:id`
  * `input (token from login) to Authorization with type bearer token`

H. Top Up(POST)
* `/admin/topup`
  * `input (token from login) to Authorization with type bearer token`
  * `{"nominal": 200000}`

I. Transfer(POST)
* `/admin/transfer`
  * `input (token from login) to Authorization with type bearer token`
  * `{receiver_phone: 08333444, nominal: 50000, note: buy a car}`
  
<br><br>

**2. USER**

A. Register(POST)
* `/register`
  * `{"username": beta, "email": beta@mail.com, "password":123}`

B. Login(POST)
* `/login`
  * `{email: beta@mail.com, password:123}`

C. Forgot Password(PATCH)
* `/forgot`
  * `{email: beta@mail.com, new_password:456, validate_password:456}`

D. Edit Profile(PATCH)
* `/profile/update`
  * `input (token from login) to Authorization with type bearer token`
  * `{you can change lastname: beta, firstname: test, phone: 083133, or picture}`

E. Show Profile(GET)
* `/profile/personal`
  * `{input (token from login) to Authorization with type bearer token}`

F. Search Receiver(POST)
* `/transaction/phone`
  * `input (token from login) to Authorization with type bearer token`
  * `{"phone": 08333444}`

G. Check Pin(POST)
* `/transaction/pin`
  * `input (token from login) to Authorization with type bearer token`
  * `{"pin": 123456}`

H. Transfer(POST)
* `/transaction/transfer`
  * `input (token from login) to Authorization with type bearer token`
  * `{receiver_phone: 08333444, nominal: 50000, note: buy a car}`

I. History Transfer(GET)
> History all
* `/transaction/history`
  * `input (token from login) to Authorization with type bearer token`

> History Week
* `/transaction/history/week`
  * `input (token from login) to Authorization with type bearer token`

> History Month
* `/transaction/history/mount`
  * `input (token from login) to Authorization with type bearer token`

<br>

## Contributors

* `Rezha Ibrahim`
* `Muhammad Abdurasyid`
* `Iqbal Athorid`
* `Furoidah Chilmi`
* `Wahyu Ramadhan`
* `Satrio Nugroho`
* `Fahmi Aziz Ismail`
