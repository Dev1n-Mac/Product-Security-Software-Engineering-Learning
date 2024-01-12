## API Client

- Responsible for assembling and directing it to the API server.


## API request

We mentioned that an API client is responsible for sending API requests in response to user actions or external events, but what, exactly, is an API request? An API request will look and behave differently depending on the type of API. That being said, an API request to a REST API is comprised of the following components:

- **Endpoint:** Every API request is directed to an [API endpoint](https://blog.postman.com/what-is-an-api-endpoint/), which is a dedicated URL that provides access to a specific resource. For instance, the /products endpoint in an e-commerce app would include the logic for processing all requests that are related to products. The request must therefore designate an endpoint so the API server knows how to proceed. We’ll discuss the API server in more detail soon.

- **Method**: Every API request must include a method, which defines the operation that the client would like to perform on the specified resource. REST APIs are accessible through standard [HTTP methods](https://blog.postman.com/what-are-http-methods/), such as GET, POST, PUT, PATCH, and DELETE, which facilitate common actions like retrieving, creating, updating, or deleting data. A GET request to the /products endpoint would tell the API server to return every product in the database.

- **Parameters**: Parameters are the variables that are passed to an API endpoint to provide specific instructions for the API to process. These parameters can be included in the API request as part of the URL, in the query string, or in the request body. For example, the /products endpoint of an e-commerce API might accept a “color” parameter, which it would use to access and return products of a specific color.

- **Request headers**: API request headers are key-value pairs that provide additional information about the request. For instance, the Content-Type header specifies the format of data in the request body, while the Authorization header provides authentication credentials, such as an [API key](https://blog.postman.com/what-is-an-api-key/) or OAuth token, to authenticate the requester.

- **Request body:** The request body includes the actual data that is necessary to create, update, or delete a resource. For instance, if an administrator of an e-commerce store needs to create a new product, the request body might include the product’s name, brand, and price. The API specification will dictate the required data format for the request, such as JSON or XML.