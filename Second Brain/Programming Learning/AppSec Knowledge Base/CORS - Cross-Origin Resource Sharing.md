
## What is the Same-Origin Policy?

- SOP is a security mechanism implemented in almost all of the modern browsers
- It does not allow documents or scripts loaded from one origin to access resources from other origins.
- Without SOP Cross-Site Request Forgery attack is relatively simple

## What is Origin?

- Two origins are considered equal if they have the same protocol, host, and port

## What is CORS?

- CORS makes it possible for a website from one origin is allowed to access resources from foreign origins.
- CORS defines 2 types of requests: **Simple Requests and Pre-flighted Requests.**
	- **Simple Requests:** A request that doesn't trigger a pre-flight request.
		- Uses a GET, HEAD, or POST method
		- Don't have headers other than the small subset defined in the specification (any custom or authorization header breaks this condition)
		- The only allowed values for Content-Type header are application/x-www-form-urlencoded, multipart/form-data, text/plain (application/json breaks this condition).
	- **Pre-flighted Requests:**  Pre-flighted requests is an HTTP OPTIONS request sent by the browser before the actual request, to check if the actual request is safe to send according to the servers CORS policy. It helps prevent unwanted or harmful requests.