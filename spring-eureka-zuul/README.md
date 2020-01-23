# Gateway service
It’s a proxy, gateway, an intermediate layer between the users and your services.

Eureka server solved the problem of giving names to services instead of hardcoding their IP addresses.

So, Zuul …

  1> Maps between a prefix path, say/gallery/** and a service gallery-service. It uses Eureka server to route the requested service.
  
  2> It load balances (using Ribbon) between instances of a service running on different ports
