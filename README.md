This project is a simple serverless API built using AWS Lambda and API Gateway.
It demonstrates how to create, deploy, and troubleshoot a cloud-based HTTP endpoint that responds dynamically to query parameters.
The API processes incoming requests and returns a JSON response with either a greeting or farewell message.

🛠️ Tech Stack
AWS Lambda – serverless compute
Amazon API Gateway – HTTP routing
Python – backend logic
CloudWatch – logging and debugging

###

⚙️ Features
Serverless architecture using AWS Lambda
RESTful endpoint via API Gateway
Query parameter handling (name, farewell)
JSON response formatting
Error handling for missing parameters
Debugging via CloudWatch logs

###

🧠 How It Works
A request is sent to the API Gateway endpoint
API Gateway forwards the request to the Lambda function
The Lambda function:
Extracts query parameters
Validates input
Constructs a response
A JSON response is returned to the client

Client Request
        |
        v
API Gateway
        |
        v
Lambda Function
        |
        v
JSON Response
        |
        v
CloudWatch Logs

###

✅ Greeting
GET /hello?name=Huzair

Response:

{
  "message": "Hello Huzair"
}
👋 Farewell
GET /goodbye?name=Huzair

Response:
{
  "message": "goodbye Huzair"
}

###

📊 Logging and Monitoring

The Lambda function uses structured JSON logging through Amazon CloudWatch.

Each request records important application events, including:

- Incoming route
- HTTP method
- Query parameters
- Response events
- Validation errors


Example log event:

{
  "event_type": "request_received",
  "data": {
    "path": "/hello",
    "method": "GET",
    "params": {
      "name": "Huzair"
    }
  }
}


CloudWatch logs are used for:
- Debugging failed requests
- Tracking API behaviour
- Investigating Lambda errors

###

🧩 Key Learnings
Understanding how API Gateway HTTP requests are passed into Lambda events
Handling query parameters and validating user input
Returning properly formatted JSON responses
Debugging common API Gateway issues (e.g., "Message: Not found")
Understanding API Gateway routing, stages, and endpoint behaviour
Structuring clean, maintainable serverless functions
Using CloudWatch logs to debug and monitor Lambda execution

###

⚠️ Challenges Faced

During development, several issues were encountered and resolved:

Fixing incorrect JSON formatting in Lambda responses
Handling None values in query parameters safely
Debugging API Gateway routing issues (404 Not Found) and understanding the difference between the API root URL and deployed routes
Ensuring correct endpoint paths and deployment stages
Understanding the structure of API Gateway HTTP API v2.0 event payload
Handling missing query parameters safely to prevent Lambda errors
Debugging Lambda execution using Amazon CloudWatch logs
Improving route handling logic to keep the Lambda function clean and maintainable
Implementing structured JSON logging to make request tracking and troubleshooting easier
Understanding Lambda execution lifecycle events, including cold starts, request IDs, and execution reports.

###

📈 Future Improvements
Add more endpoints (e.g., /info)
Integrate with a database (DynamoDB)
Add authentication (JWT / Cognito)
Improve input validation
Deploy using Infrastructure as Code (Terraform / AWS SAM)

###

🚀 Deployment
Create Lambda function
Attach handler
Configure API Gateway routes (/health, /test, /hello, /goodbye)
Deploy to a stage (e.g., dev)
Invoke via: https://<api-id>.execute-api.<region>.amazonaws.com/dev/test
