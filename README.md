# image-catalogue-microservice
Spring boot based image catalogue micro service 

# Eureka Server
Every service registers itself with Eureka, and pings Eureka server to notify that it’s alive.

# Image Service
The image service acts as a data source for images, each image has an id, title, and url. Image service has exposed some data through endpoints

# Gallery Service
The gallery service calls image service to get a list of all images, or maybe only images created during a specific year.
The calls from this REST client to the other services can be done using:

  1> RestTemplate. An object that’s capable of sending requests to REST API services.
  
  2> FeignClient (acts like a proxy), and provides another approach to RestTemplate.
  
Both, load balance requests across the services.

# Gateway service
It’s a proxy, gateway, an intermediate layer between the users and your services.

Eureka server solved the problem of giving names to services instead of hardcoding their IP addresses.

So, Zuul …

  1> Maps between a prefix path, say/gallery/** and a service gallery-service. It uses Eureka server to route the requested service.
  
  2> It load balances (using Ribbon) between instances of a service running on different ports
  
  
# Auth Service
In the auth service, we:

  1> validate the user credentials, and if valid, 

  2> generate a token, otherwise, throw an exception.
  
 # Common Service
We have common configuration variables, enum classes, or logic, used by multiple services, like the one we had JwtConfig. Instead of duplicating the code, we put it in a separate service that can be included and used as a dependency in other services.


