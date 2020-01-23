# Gallery Service
The gallery service calls image service to get a list of all images, or maybe only images created during a specific year.
The calls from this REST client to the other services can be done using:

  1> RestTemplate. An object that’s capable of sending requests to REST API services.
  
  2> FeignClient (acts like a proxy), and provides another approach to RestTemplate.
  
Both, load balance requests across the services.
