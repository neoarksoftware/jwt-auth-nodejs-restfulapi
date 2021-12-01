MIT License

Copyright (c) 2021 Neoark

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


 
 Development Environment & Disclaimer!
 -------------------------------------
 _It is an open source SAMPLE SCRIPT and the used development environment is `Node with 
 ExpressJS, Linux (Ubuntu-18.04 OR Ubuntu-20.04), MongoDB, JSON WebToken, BcryptJS
 etc`, however, author neither warranty nor recommend the script for the stagging 
 and/or for the production development environment._ 
 
 * @package     SAMPLE SCRIPT
 * @author      Development Team @Neoark Software Pvt Ltd
 * @license     http://opensource.org/licenses/MIT
 * @questions:  http://www.support.gowithexperts.com
 * @link        http://www.neoarks.com
 * @since       Version 1.0.0
 * Year: Novemver, 2021
 * @filesource
 ------------------
 

🙌 Prerequisites:
----------------
The prerequisites `(NodeJS, Angular CLI, Git, Browser etc)` must installed already on the development environment. If these prerequisites are not available yet, please install them and then proceed below mentioned Installation steps.


Installation Steps/Guide:
------------------------
1. cd /var/www/html/                                                            [Optional - move to DocumentRoot directory]
2. git clone https://github.com/neoarksoftware/jwt-auth-nodejs-restfulapi.git   [OR Download `main` branch code]
2. cd jwt-auth-nodejs-restfulapi
3. npm install
4. Run project by node index.js OR nodemon

Using Postman OR Talend API Tester(Google Chrome Extension) to test the endpoint, Below are the request and respose of the registration and login and welcome apis

Registaration API 
------------------
```
URL: http://localhost:4001/register
Method: POST
Request params:
{
  "first_name": "Test",
  "last_name": "User",
  "email": "testuser@gmail.com",
  "password": "test@user123"
}

Response:
{
  "first_name": "Test",
  "last_name": "User",
  "_id": "61a0a9162ccfa840d8239a3d",
  "email": "testuser@gmail.com",
  "password": "$2a$10$DJIX.8ptwWV6L2yLO8zCi.hgrloHDG5KJDV4TWQq/0Az5ZpVqLQum",
  "__v": 0,
  
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNjFhMGE5MTYyY2NmYTg0MGQ4MjM5YTNkIiwiZW1haWwiOiJ0ZXN0dXNlckBnbWFpbC5jb20iLCJpYXQiOjE2Mzc5MTg5OTgsImV4cCI6MTYzNzkyNjE5OH0.\_VR8vaCJQhikj1kaLyDhc7DK0nqcUSRd07lbF-hXRTs"
}
```
Login API
---------
```
URL: http://localhost:4001/login
Method: POST
Request: 
{
  "email": "testuser@gmail.com",
  "password": "test@user123"
}

Response:
{
  "first_name": "Test",
  "last_name": "User",
  "_id": "61a0a9162ccfa840d8239a3d",
  "email": "testuser@gmail.com",
  "password": "$2a$10$DJIX.8ptwWV6L2yLO8zCi.hgrloHDG5KJDV4TWQq/0Az5ZpVqLQum",
  "__v": 0,
  
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNjFhMGE5MTYyY2NmYTg0MGQ4MjM5YTNkIiwiZW1haWwiOiJ0ZXN0dXNlckBnbWFpbC5jb20iLCJpYXQiOjE2Mzc5MTkxNDEsImV4cCI6MTYzNzkyNjM0MX0.LIO-rJFBUkb6q1qlLB_IwXQId3vMG0cGqUqt_1gKRlk"
}
```

Welcome API
----------------
```
URL: http://localhost:4001/welcome
Method: POST
Headers: 
{
    "x-access-token": jwt token value provided in login api response
}
Note: Request body is empty in this demo project, but you can build according to your need
Response: Welcome 🙌 
```