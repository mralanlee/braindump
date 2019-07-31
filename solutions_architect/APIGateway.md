# API Gateway
- Fully managed services for devs to publish, maintain, monitor, and secure APIs at any scale
- Few clicks in AWS Management Console, you can:
  - create an API that acts as a "font door" for apps to access data
  - Business Logic
  - Functionality from back-end services (EC2, Lambda, or any web app)
  - Low cost and efficient
- Scales Effortlessly
- Throttle Requests to prevent attacks
- Connect to CloudWatch to log all requests

## API Caching
- Caching to the endpoint response
- Reduce the number of calls made to endpoint
- Improve latency on request to API
- When enabling caching for a stage, API Gateway caches response frmo your end point to a specified TTL period  in seconds.
- API Gateway responds to the requests by looking up endpoing response from cache instead of making a request from endpoint


#### Same Origin Policy
Under policy, browser permits scripts contained in a first web page to access data in a second webpage, only if it has the same origin

#### CORS (Cross Origin Resource Sharing)
- Relax the same origina policy
- Allows restricitred resources on a webpage to be requested from another domain outside the domain from which the first was served


### Exam Tips
- API Gateway has caching capabilities to increase performance
- Low costs and scales automatically
- Throttle API gateway to prevent attacks is possible
- You can log results to CloudWatch
- Javascript/AJAX that uses multiple domains with API gateway, ensure CORS is enabled
