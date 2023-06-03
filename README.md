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

Handles user registration, authentication, and vehicle registration functionalities. Provides loosely coupled data for other services to use.

<h3> Ride Request Service: </h3>

Manages ride requests issued by passengers, storing request details and publishing them for other services.

<h3> Recommendation Service: </h3>

Provides a recommended list of passengers to drivers based on various factors such as distance, trip fare, and passenger ratings. Uses data from ride requests, user ratings, and vehicle details.

<h3> Match Ride Service: </h3>

Matches drivers with selected passengers and verifies their points for payment. Stores approved rides and sends map routes to drivers. Listens to authentication and top-up services for user and point details.

<h3> Payment Service: </h3>

Handles point deduction for completed trips. Generates QR codes for payment and deducts points from passenger accounts. Listens to data from the Match Ride and Top Up services.

<h3> Top Up Service: </h3>

Allows passengers to top up their points by entering bank details. Listens to data from the Payment Service and publishes updated available points.

<h3> Review Service: </h3>

Manages user reviews and ratings. Processes and stores reviews in the database. Listens to data from the Match Ride service and publishes review and ratings for other services.

<h3> Payment Service: </h3>

The Payment Service handles the payment functionality within the RideShare Application. It integrates with payment gateways or third-party payment providers to facilitate secure and convenient payment transactions. The service generates QR codes for payment and deducts points from the passenger's account for completed trips.

<h3> Review Service: </h3> 

The Review Service manages the review and rating system within the application. It allows both passengers and drivers to provide feedback and ratings after completing a ride. The service stores and processes the reviews, enabling users to make informed decisions when selecting future rides.


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
<!--  -->
								kubectl apply -f service-name.yaml
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

