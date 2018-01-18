# Angular4 With SpringBoot Microservice

Sample application for viewing the Vehicle details and current status.
Vehicle Service contains the details of Vehicles – Vehicle ID, Status, Registration number along with the customer ID – Foriegn key  to the customer details.

Customer details are retrieved from Customer Service using Feign Client(CustomerApi). 

Random vehicle status, Active and Disconnected updated for every minute.
For the services registration and identification created Discovery service.
As it is a small application and implemented without authentication services such as OAuth2, merged Gateway service with Discovery Service. 

# DB and JPA:
Used in memory database derby for storing the Vehicle and Customer details. 
Entity and table reference created in Vehicle.java and customer.java. 
Accessed the same using VehicleRepository and CustomerRepository. All CRUD operations are handled using these Repositories. 

# Unit Testing: 
Implemented unit testing using MockMvc in repositories, controller for both Customer and vehicle Service.

# UI: 
Used Angular 4 and ngx datatable for displaying the Vehicle Details.  
Implemented multiple column sorting and data can be filtered based on Customer name and Vehicle Status column.

# Deployment Steps:
Open seperate command prompt for each service and change the path to respective  target folder. 
Ex: cd ..\discovery-service\target.
All the Jars are available in respective target folder. 
Run DiscoveryService, Customer Service, Vehicle Service using their Jars using the command java -jar <jar name>
  
Please note that as Vehicle Service depends on Customer and Discovery Service, run the service as per above sequence.

Once all services are started, Angular application can be started using Node server. 
Open command Prompt and go to the project path and run 
1. npm install
2. ng serve. 

Application available in http://localhost:4200/ 
