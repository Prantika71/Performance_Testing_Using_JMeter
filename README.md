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
 Create a Collection of APIs (JMeter Collection) of Login API, Create Booking API, and Search API HTTP requests.
 1. Add the following properties to the Header Controller:
 ```plaintext
Accept: */*

 ```plaintext
2. Login
Request URL:
https://restful-booker.herokuapp.com/auth

Pre-request Script:
{
  "body": {
    "username": "admin",
    "password": "password123"
  }
}






