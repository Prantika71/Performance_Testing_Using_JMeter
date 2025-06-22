# **Performance Testing Using JMeter**

## **Content**
 - [Introduction](#Introduction)
 - [Test Case Scenario](#Test-Case-Scenario)
    - [Test Cases Scenario - Restful-Booker](#test-cases-scenario---restful-booker)
    - [Test Cases Scenario - DMoney Transaction APIs](#test-cases-scenario---dmoney-transaction-apis)
 - [How to Run This Project](#how-to-run-this-project)
    - [Using JMeter](#using-jmeter)
    - [Using CLI](#using-jmeter)
 - [Technology Used](#Technology-used)
 - [Load and Stress Test Excel Report](#load-and-stress-test-excel-report)
 - [HTML Report Generate](#html-report-generate)
    - [Generated HTML report for Load Test](#generated-html-report-for-load-test)
    - [Generated HTML report for Stress Test](#generated-html-report-for-stress-test)
    - [Generated HTML report for DMoney JMeter Collection Test](#generated-html-report-for-dmoney-jmeter-collection-test)


---

## **Introduction**
For this project, 
- **Restful-Booker**: A Books API for load testing and Stress testing
- **Dmoney** A Website Transaction API for API Chainning (JMeter Collection). Also, I have taken CSV data files to run multiple APIs using Three Threads (Deposit, SendMoney, and Payment) in Jmeter, For Transaction APIs.

## **Test Case Scenario**
# **Restful_Booker**
 -- Create a Collection of APIs (JMeter Collection) of Login API, Create Booking API, and Search API HTTP requests.
### _**1. Add the following properties to the Header Controller:**_
 ```console

Accept: */*

```

### _**2. Login**_
Request URL:
#### Request URL: **https://restful-booker.herokuapp.com/auth**

Pre-request Script:
```console
{
  "body": {
    "username": "admin",
    "password": "password123"
  }
}
```
### _**3.Create Booking**_

#### Request URL: **https://restful-booker.herokuapp.com/booking**
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
### _**4.Search Booking**_
#### Request URL: **https://restful-booker.herokuapp.com/booking/bookingid**
and **Scenario:** **120,000 users** over a **12-hour** period log in, create a booking, and search for the booking. 

## **Test Cases Scenario - DMoney Transaction APIs**

### Dmoney Transactions APIs:
1. Admin creates an Agent, 2 random Customers, and a Merchant.  
   - **Admin email**: `admin@roadtocareer.net`  **Password**: `1234`
2. Deposit some money from the SYSTEM account to the Agent.  
   - **System account**: `SYSTEM`  **Range**: 10 TK to 10,000 TK
3. Agent deposits money to one of the Customers.
   - **Hint**: fromAc: `Agent`, toAc: `Customer`     
4. Then, send money from one Customer to another Customer.
   - **Hint**: fromAc: `Customer`, toAc: `Customer`  
5. Make a payment from the second Customer to the Merchant.
   - **Hint**: fromAc: `Customer`, toAc: `Merchant`

### **Scenario**: 
○ 5 agents perform deposits for 10 customers.
○ 5 customers send money to another 10 customers.
○ 5 customers make payments to 2 merchants.

## How to run this project
### Using JMeter:
- clone this project
   ```console
   
     https://github.com/Prantika71/Performance_Testing_Using_JMeter
   
    ``` 
- Open Apache Jmeter 
- From Jmeter Click on Open then open the JMX file
- Run the file

  - **For Booking APIs JMeter Collection:
  ```console
   jmeter -n -t .\Booking.jmx -l .\Booking.jtl -e -o Reports
  ```
   - ***For Booking APIs JMeter Collection:**
 ```console
jmeter -n -t .\Dmoney.jmx -l .\Dmoney.jtl -e -o Reports
 ```
## Technology Used
- Jmeter: If you haven't already, [download and install Jmeter - ](https://jmeter.apache.org/download_jmeter.cgi)
    - Search For **Binaries:** Then --> **apache-jmeter-5.6.3.zip**
- Postman: If you haven't already, [download and install Postman.](https://www.postman.com/downloads/)
  
## **Load and Stress Test Excel Report**
For the Load test and Stress test Excel report check the link - 
[view excel report file](https://docs.google.com/spreadsheets/d/1DYxrmWinmbZg5xTTA2m1FdvcTpX5NXieUWaZVdx-ppk/edit?gid=1931672790#gid=1931672790)

## **HTML Report Generate**
### Load Testing HTML Report
![image](https://github.com/user-attachments/assets/a8832730-c6df-4f6c-8609-b726caefbf49)


### Stress Testing HTML Report
![image](https://github.com/user-attachments/assets/17f67bef-6819-4668-80db-6709b3af3e1b)

Since this is a public server, while I was doing stress testing, the server behaved unexpectedly, and I couldn't execute stress tests properly. Whenever I increase the number of users above 4000, it suddenly shows an error rate of 0%, and after 10000 users, it shows  an error rate above 1%. So for me finding a bottleneck becomes very difficult and I need to consider the bottleneck point at 4000 users with an error rate of 0.03%. 


### Generated HTML report for DMoney Jmeter Collection Test
![image](https://github.com/user-attachments/assets/0e37e706-3a3d-4b17-a6df-7b57cf70fb22)










