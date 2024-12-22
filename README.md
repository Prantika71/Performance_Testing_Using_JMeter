# Permonce Testing Using JMeter

## Content
## Introduction
## Test Case Scenario
## Technology Used
## Load and Stress Test Excel Report
## HTML Reports


---

## Introduction
For this project, 
- Restful-Booker: A Books API for load testing and Stress testing
- Dmoney A Website Transaction API for API Chainning (JMeter Collection). Also, I have taken CSV data files to run multiple APIs using Three Threads (Deposit, SendMoney, and Payment) in Jmeter, For Transaction APIs.

## Test Case Scenario
# Restful_Booker
 -- Create a Collection of APIs (JMeter Collection) of Login API, Create Booking API, and Search API HTTP requests.
 1. Add the following properties to the Header Controller:
 ```

Accept: */*

```

2. Login
Request URL:
https://restful-booker.herokuapp.com/auth

Pre-request Script:
```
{
  "body": {
    "username": "admin",
    "password": "password123"
  }
}
```
Create Booking:
○ URL: https://restful-booker.herokuapp.com/booking
○ Body:
```
{
"firstname": "Generate Random FirstName",
"lastname": "Generate Random LastName",
"totalprice": Generate random amount,
"depositpaid": true,
"bookingdates": {
"checkin": "2024-01-01",
"checkout": "2024-01-02"
}
}
```
Search Booking:
- URL: https://restful-booker.herokuapp.com/booking/<booking_id&gt;
- 120,000 users over a 12-hour period log in, create a booking, and search for the
booking. 

# Dmoney Transactions APIs
- Admin creates an Agent, 2 random Customers, and a Merchant.
-- Admin email: admin@roadtocareer.net Password: 1234
- Deposit some money from the SYSTEM account to the Agent.
--System account: SYSTEM Range: 10 TK to 10,000 TK
- Agent deposits money to one of the Customers.
--Hint: fromAc: Agent, toAc: Customer
- Then, send money from one Customer to another Customer.
--Hint: fromAc: Customer, toAc: Customer
- Make a payment from the second Customer to the Merchant.
-- Hint: fromAc: Customer, toAc: Merchant


# Technology used
- Jmeter: download and install Jmeter -
Search For Binaries: Then --> apache-jmeter-5.6.3.zip
- Postman: download and install Postman.
# Load and Stress Test Excel Report
For the Load test and Stress test Excel report check the link - 
[view excel report file](https://docs.google.com/spreadsheets/d/1DYxrmWinmbZg5xTTA2m1FdvcTpX5NXieUWaZVdx-ppk/edit?gid=1931672790#gid=1931672790)

## Load Testing HTML Report
![image](https://github.com/user-attachments/assets/a8832730-c6df-4f6c-8609-b726caefbf49)


## Stress Testing HTML Report
![image](https://github.com/user-attachments/assets/17f67bef-6819-4668-80db-6709b3af3e1b)


## HTML Reports
### Generated HTML report for DMoney Jmeter Collection Test
![image](https://github.com/user-attachments/assets/0e37e706-3a3d-4b17-a6df-7b57cf70fb22)










