# avtobusi
Web application for intercity bus lines in Macedonia

The application is started using spring web but we want to upgrade later to spring web. 

Also we want to use event driven programming using axon or kafka, in combination with CQRS, so that when 
a passenger books a trip the booking, and later update of ticket availability is done with the help of CQRS. 

Beside axon and kafka we might want to investigate other similar technologies and frameworks, such as 
RabbitMQ, ActiveMQ, Akka, Protobuf. 

For the front end part we want to use Angular framework, in combination with spring boot for the backend.
The application will be deployed to the cloud, on kubernetes cluster, now, on which cloud, that's a question, 
but we would like to have at least two components, one for the front end, built in angular, and another one,
for the backend built in spring boot. 


I want to have bus line like this

Negotino - Skopje, without date. 

It should give a list of all bus lines from Negotino to Skopje, for each day of the week with departure time and arrival time
the web site should provide info on all the bus stops with exact times of arrival at the stop, and departure from the stop.
The bus stop can be another place (town, village, or station)

so for Negotino - Skopje we'll have
- Negotino Bus Station
- Gradsko Bus Station
- Veles Bus Station
- Skopje City Bus Station

place Negotino, Gradsko, Veles, Skopje
station Negotino Bus Station, Gradsko Bus Station, Veles Bus Station, Skopje, Bus Station

bus line Negotino - Skopje
stops:
1. Negotino bus station
2. Gradsko bus station
3. Veles bus station
4. Skopje city bus station

tables

station
stop
line 
place


The first step in building this application will be to have an api endpoint. 
The endpoint should accept departure place name and arrival place name. 
Then the application should fetch the data regarding the departure station and the arrival station.
The data returned will be in JSON format or protobuf, and will have info like
 - departure station, time of departure, bus stops, carrier name and info, arrival station and time of arrival. 
There should be a unit test for this, which will simulate the behavior. 