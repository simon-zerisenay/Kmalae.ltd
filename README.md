# Kmalae.ltd
Kmalae.ltd
<p align="center">
	<img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/simon-zerisenay/Kmalae.ltd?color=lightblue" />
	<img alt="Number of lines of code" src="https://img.shields.io/tokei/lines/github/simon-zerisenay/Kmalae.ltd?color=critical" />
	<img alt="Code language count" src="https://img.shields.io/github/languages/count/simon-zerisenay/Kmalae.ltd?color=yellow" />
	<img alt="GitHub top language" src="https://img.shields.io/github/languages/top/simon-zerisenay/Kmalae.ltd?color=blue" />
	<img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/simon-zerisenay/Kmalae.ltd?color=green" />
</p>
<h1> Project Name: Kmalae Carpooling Application </h1>

<div align="center">

<a href="https://github.com/kmalae/Kmalae" target="_blank">
    <img src="https://github.com/simon-zerisenay/simon-zerisenay/blob/main/kmalae.png"   padding="20" height="170" width="200" alt="twitter logo"  />
  </a>
	
</div>


<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/watch?v=f2IfhkPqWFU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>



The Kmalae Carpooling Application is a solution aimed at reducing the number of vehicles on the road, thereby reducing carbon dioxide (CO2) emissions and mitigating air pollution. The application provides a platform for people to share rides, allowing passengers to tag along with drivers heading to the same destination. By implementing this solution, the application contributes to a sustainable and greener environment by significantly reducing vehicle-caused carbon emissions.

The application also offers financial benefits to both drivers and passengers. Drivers can save on car-related expenses, particularly with the rising gasoline prices, while passengers can enjoy cheaper transportation compared to other modes of transport like taxis. The expenses are shared among all the riders, making it an economical choice.

<h2> Key Environmental Impact: </h2>

<h3> Carbon Emissions: </h3>
Vehicles are a significant source of carbon dioxide emissions, contributing to global warming and air pollution. The RideShare Application helps reduce the number of vehicles on the road, resulting in a substantial decrease in CO2 emissions.

<h3> Air Pollution: </h3>

Vehicle emissions contribute to air pollution, which has adverse effects on human health and the environment. Air pollutants can lead to respiratory diseases, damage to organs, and harm to crops and trees. By reducing the number of vehicles through ride-sharing, the application helps mitigate air pollution and its associated risks.

<h3> Sustainability: </h3>

The production and consumption of gasoline vehicles hinder sustainability and green environment initiatives. The RideShare Application provides an alternative solution that promotes sustainable transportation by maximizing the use of existing vehicles and reducing the need for new ones.

<h3> Financial Benefits: </h3>

Cost Savings for Drivers: By sharing rides, drivers can save significant car-related expenses, especially with the rising gasoline prices. The application offers a platform for drivers to find passengers heading in the same direction, allowing them to share the costs of fuel and maintenance.

Affordable Transportation for Passengers: The RideShare Application provides passengers with a cheaper transportation option compared to taxis and other competitive modes of transport. The expenses are distributed among all the riders, making it an economical choice for passengers.

<h2> Application Architecture: </h2>

The RideShare Application follows a services-based design, leveraging the microservices architecture. The application consists of seven services that work together to provide the desired functionality:

<h3> Authentication Service: </h3>
The functionality of this service is for user registration and authentication. Users (driver/passenger) can sign up and sign in through this service. This service also handles car registration functionalities, where users can register, update, and delete their vehicles on the system. The service uses collections (database) named User and Vehicle. Once a user or a vehicle is registered on the system, the service publishes the data for other services to use, the concept of loosely coupled. Below is the Hierarchical File structure of Authentication service: 
Handles user registration, authentication, and vehicle registration functionalities. Provides loosely coupled data for other services to use.
<br/>
<h4> Routers: </h4> This folder contains two directories i.e., users and vehicles 
<h4> Users: </h4> This directory has routes which are used for user registration and authentication.
<h4> Current user: </h4> This route can be used to retrieve all the information provided by the user.
<h4> Get-info: </h4> Users use this page to get all the information they have with us/in our database. 
<h4> Sign in: </h4> This route serves as a point for users to signin to the application. If they have unexpired cookie, they don’t need to login again. 
<h4> Sign out: </h4> if the users want to logout from the application this route is activated. This route destroys the cookie so that the users cannot use the application without sign in. 
<h4> Signup: </h4> This is one of the principal routes which is also known as registration page as it enables users and organisations to independently register and gain access to the system.
<h4> Update-info: </h4> Users can use this page to update the information they previously provided. 
<h4> Update-password: </h4> This route is for the users who want to change their password or who are forced to change their password. 
<h4> Vehicles: </h4> This directory has routes for users to register their vehicles. Users are required to register vehicle if they want to give a ride. 
<h4> Delete-vehicle: </h4> As it is name indicates, this router is for the users to delete one of the vehicles they have previously registered.
<h4> Get-user-vehicle: </h4> This route is used to render the list of vehicles owned by the specific user. 
<h4> Get-vehicle-info: </h4> This route renders the detailed information about a specific vehicle. 
<h4> Register-vehicle: </h4> This is the principal route in this directory. Users use this route to register their vehicle. Users can register multiple vehicles. 
<h4> Update-vehicle: </h4> This route is used to update the vehicle information for one of their vehicles.
<h4> Services: </h4> Password.ts file is used to hash the password by adding salt to make it more secure so that it can’t be easily brute forced by attackers. Moreover, we use it to compare the passwords inputted and stored in our database when the user is signing in. 

<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/Authentication.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>
<h3> Ride Request Service: </h3>

Manages ride requests issued by passengers, storing request details and publishing them for other services.

This service handles the ride requests issued by the passenger. The passenger can request a ride by providing the pickup and drop-off location and desired departure time. Then the service stores the request details into the Ride Request Details database and publishes passenger ID and ride request details for other services to use.

Routers directory of ride request service contains five routes. 
<br/>
Cancel-ride-request: Users who pose as passengers can cancel the ride, they requested by using this route. 
<br/>Create-ride-request: Users can send a ride request to the drivers initially by creating a ride request. They need to input their pickup point, destination, and time of departure in order to successfully request for a ride.  
<br/>Get-ride-request: Users can see a detailed information about one of their ride requests. 
<br/>Get-user-ride-requests: This route is used by users who are using the application as passengers to see the list of rides requests, they made. 
<br/>Update-ride-request: Users can use this route to update their ride request i.e (pickup point, destination and time of departure)
<br/>
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/RideRequest.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>
<h3> Recommendation Service: </h3>

Provides a recommended list of passengers to drivers based on various factors such as distance, trip fare, and passenger ratings. Uses data from ride requests, user ratings, and vehicle details.

This service handles two functionalities which are lift requests and providing mutual ride data. In the lift request functionalities this service enables drivers to create, update and delete a lift request. On the second functionalities, this service computes and retrieves set of rides that has a mutual time of departure and destination with a given lift request.

Routes: this service contain routes that are categorized as lift-request and ride-data.
<br/>
Lift-request: this folder contains all routes related to lift requests manipulation.
<br/>
Create-lift-request: this route enables drivers to create lift requests by providing necessary details such as starting and destination locations, time of departure and others.
<br/>
Update-lift-request: this route enables driver to update any of the created lift requests.
<br/>
Get-lift-request: this route retrieves a specific lift request specified by lift request ID from database. The aim of this route is to provide the user with the details of a lift-request during updating it.
<br/>
Get-user-lift-request: this route retrieves all lift requests that are created by the specific user. The aim of this route is to provide the driver with a list of all available (not cancelled) lift requests.
<br/>
Cancel-lift-request: this route enables the driver to delete created lift requests.
<br/>
Ride Data: this folder contains routes that compute and retrieve set of rides that has a mutual destination (as per the driver specified radius) and time of departure (5 minutes before and after the driver’s time of departure)
<br/>
Get-mutual-requests: this route takes the driver’s destination and time of departure as parameters and retrieves all ride requests made by passengers that have mutual destination and time of departure as described above. Later, the data retrieved by this route along with the data retrieved by the two below routes is used in the recommendation process at the front end. The recommendation process in the front end consumes the data to provide the driver with a list of recommended passengers to take for every lift request.
<br/>
Get-driver-vehicle: this route provides the details of a specific vehicle which is specified by the driver to be used in a specific lift request. The retrieved data of this route is later fed to the frontend recommendation system with details of the a car that is required in the recommendation process such as ( model, brand name, luxury status, fuel consumption and so on.
<br/>
Get-passenger-review: this route retrieves all the reviews a specific passenger accumulated on every trip taken.
<br/>
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/Recommendation.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>
<h3> Match Ride Service: </h3>

Matches drivers with selected passengers and verifies their points for payment. Stores approved rides and sends map routes to drivers. Listens to authentication and top-up services for user and point details.

The service stores the approved rides in the Approved Rides database and publishes it. After that, this service sends a map route to the pick-up point to the driver. The service always listens to data published by Authentication and Top Up services to obtain data about the users (passenger and driver details) and available points of passengers, respectively. The service handles the request made by the driver to set passengers to form a shared trip. It also handles the accept or reject response of each passenger to the request made by the driver. Besides, this service enables both driver and passenger to cancel previously agreed trips in a 5 minute time window starting from the requested initiated time.


<b>Routes:</b> This service contains 4 routes (API interfaces) as detailed below:
<b>Create-match-requests:</b> this route enables the driver to request a passenger in a specific trip (ride and lift requests with mutual destination and time of departure). The meaning of the request is that the driver is interested in giving a lift to the passenger.
<b>Passenger-confirm-request:</b> this route enables a passenger to either accept or request the request made by a driver as described above.
<b>Driver-cancel-request:</b> this route enables drivers to cancel the request made above.
<b>Passenger-cancel-request: </b>this route enables the passenger to cancel the either accept or reject response they gave to the driver request.


<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/MatchRide.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>
<h3> Payment Service: </h3>

Handles point deduction for completed trips. Generates QR codes for payment and deducts points from passenger accounts. Listens to data from the Match Ride and Top Up services.

The Payment service handles the point deduction process after every completed trip. Upon reaching the destination, the driver provides the drop-off location to the service. The service then calculates the trip fare and generates a QR code, where the passenger makes the payment by scanning it. After passengers scan the QR code, the system deducts the points from their account and publishes the remaining points to other services. This service listens to data published by the Match Ride and Top Up services.

Routers directory of Payment service only contains one route which is deduct-points.
Deduct-points: This router is a principal route which is used by users who pose as passengers and drivers to make transaction/payment. Whenever a user pays another user, it deducts points from his account and adds it to the other user. 


<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/Payment.png" align="center" width="480" height="780" alt="redux" />
	<br/>
<h3> Top Up Service: </h3>
Allows passengers to top up their points by entering bank details. Listens to data from the Payment Service and publishes updated available points.
The Top Up service is used by passengers to get points by entering their bank details. The points equal to the amount of money paid in the transaction. This service listens to data published from the Payment Service. It also publishes the updated available points for other services to use.

Routers directory of Top-up service only contains one route which is perform-topup.
Perform-top-up: Users use this route to top up money from their debit/credit card to our system. The system saves the money in points. The user can then use the points to make any kind of payment in this application.  
	
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/TopUp.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>
<h3> Review Service: </h3>

Manages user reviews and ratings. Processes and stores reviews in the database. Listens to data from the Match Ride service and publishes review and ratings for other services.
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/Review.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>

<h3> Review Service: </h3> 

The Review Service manages the review and rating system within the application. It allows both passengers and drivers to provide feedback and ratings after completing a ride. The service stores and processes the reviews, enabling users to make informed decisions when selecting future rides.
	
The Review service handles users' reviews and ratings. The service receives reviews and ratings from both passengers and drivers. It then processes and stores it in the Reviews database. This service listens to data published by Match Rides Services. It also publishes the review and ratings under the passenger ID to be used by other services.
	
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/Review.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>

<h3> Mobile Client </h3>
<div align="center">
<img src="https://github.com/simon-zerisenay/Kmalae.ltd/blob/main/MobileClient.png" align="center" width="480" height="780" alt="redux" />
	<br/>
</div>

<h2> Backend Structure Overview: </h2>

The project structure consists of the seven services along with two additional components, the infra and library.

<h3> Infra: </h3>

Contains Kubernetes configuration files for each service, specifying details required for deployment and maintenance in the Kubernetes cluster.

<h3> Library: </h3>

Contains reusable code pieces categorized as errors, events, middleware, services, and types.

overview of the RideShare Application, highlighting its key features, deployment instructions, and technologies used.

<h2> Key Features: </h2>

<h3> User Registration and Authentication: </h3>

The application allows users to register and authenticate themselves using secure authentication mechanisms, ensuring the privacy and security of user data.

<h3> Ride Request and Matching: </h3>

Passengers can submit ride requests, specifying their pick-up and drop-off locations. The Recommendation Service matches the passengers with suitable drivers based on various factors such as distance, trip fare, and passenger ratings.

<h3> Route Planning and Navigation: </h3>

Once a ride is matched, the Match Ride Service generates the optimal route for the driver to follow. The route is communicated to the driver through map routes, ensuring efficient and accurate navigation.

<h3> Point-based Payment System: </h3>

The application uses a point-based payment system, where passengers earn points for sharing rides and can use these points to pay for future rides. The Payment Service handles the deduction of points for completed trips and generates QR codes for payment.

<h3> Review and Rating System: </h3>

After completing a ride, both passengers and drivers can provide reviews and ratings for each other. The Review Service manages the storage and processing of these reviews, allowing users to make informed decisions when choosing future rides.

<h2> Deployment Instructions: </h2>

To deploy the RideShare Application, follow these steps:

<h3> Set up the Kubernetes cluster: </h3>

Ensure you have a Kubernetes cluster up and running to deploy the application. You can use cloud providers like Amazon EKS, Google Kubernetes Engine, or set up a local cluster using tools like Minikube or Docker Desktop.

<h3> Configure the infrastructure: </h3> 

Navigate to the "infra" directory and update the Kubernetes configuration files for each service with the appropriate configurations for your environment. This includes specifying resource limits, environment variables, and service dependencies.

<h3> Deploy the services: </h3>

Use the Kubernetes command-line tool (kubectl) to deploy each service to the cluster. Run the following command for each service:  
Or Use skaffold start:
		
								skaffold start
								  npm start
<h3> Monitor the deployment: </h3>

Use Kubernetes tools or monitoring solutions to monitor the deployed services and ensure they are running correctly. Check the logs for any errors or issues during the deployment process.

<h3> Test the application: </h3>

Once the services are deployed and running, test the application by registering users, issuing ride requests, and verifying the functionality of key features such as ride matching, payment, and reviews.

<h2> Technologies Used: </h2>

The RideShare Application leverages the following technologies:

<h3> Backend: </h3>
The backend services are developed using a microservices architecture and are implemented using popular programming languages and frameworks such as Node.js, Python, or Java. The choice of technology depends on the specific service requirements and team preferences.

<h3> Kubernetes: </h3>
The application is deployed and managed using Kubernetes, an open-source container orchestration platform. Kubernetes provides scalability, high availability, and easy management of the application services in a distributed environment.

<h3> Authentication and Security: </h3>

Secure authentication mechanisms, such as JWT (JSON Web Tokens), are used for user registration and authentication. Additional security measures, such as HTTPS, encryption, and input validation, are implemented to ensure data privacy and protection.

<h3> Database: </h3>

A suitable database system, such as MySQL, PostgreSQL, or MongoDB, is used to store user data, ride requests, reviews, and other relevant information. The choice of the database depends on the specific requirements of the application.

<h3> Mapping and Navigation: </h3> 

Mapping and navigation services, such as Google Maps API or Mapbox, are integrated into the application to provide route planning, real-time navigation, and distance calculations for ride matching and driver directions.

<h3> Messaging and Event-Driven Architecture: </h3>

Message brokers, such as RabbitMQ or Apache Kafka, are used for inter-service communication and event-driven architecture. They enable the exchange of messages between services and facilitate loose coupling and scalability.

