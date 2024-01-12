
 - ==Horizontal scaling means that you scale by adding more machines into your pool of resources whereas “vertical” scaling means that you scale by adding more power (e.g., CPU, RAM) to an existing machine.==
- Load Balancers route incoming requests to one of many application servers that are typically clones / mirror images of each other and send the response from the app server back to the client. Any one of them should process the request the same way so it’s just a matter of distributing the requests across the set of servers so none of them are overloaded.