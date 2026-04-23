This project is a simple serverless API built using AWS Lambda and API Gateway.
It demonstrates how to create, deploy, and troubleshoot a cloud-based HTTP endpoint that responds dynamically to query parameters.
The API processes incoming requests and returns a JSON response with either a greeting or farewell message.

🛠️ Tech Stack
AWS Lambda – serverless compute
Amazon API Gateway – HTTP routing
Python – backend logic
CloudWatch – logging and debugging

⚙️ Features
Serverless architecture using AWS Lambda
RESTful endpoint via API Gateway
Query parameter handling (name, farewell)
JSON response formatting
Error handling for missing parameters
Debugging via CloudWatch logs

🧠 How It Works
A request is sent to the API Gateway endpoint
API Gateway forwards the request to the Lambda function
The Lambda function:
Extracts query parameters
Validates input
Constructs a response
A JSON response is returned to the client

✅ Greeting
GET /test?name=Huzair

Response:

{
  "message": "Hello Huzair"
}
👋 Farewell
GET /test?name=Huzair&farewell=true

Response:
{
  "message": "Goodbye Huzair"
}

🧩 Key Learnings
Handling event input structure in Lambda (queryStringParameters)
Returning properly formatted JSON responses
Debugging common API Gateway issues (e.g., "Message: Not found")
Understanding routing and stage URLs in API Gateway
Structuring clean, maintainable serverless functions

⚠️ Challenges Faced
Fixing incorrect JSON formatting in Lambda responses
Handling None values in query parameters safely
Debugging API Gateway routing issues (404 Not Found)
Ensuring correct endpoint paths and deployment stages
