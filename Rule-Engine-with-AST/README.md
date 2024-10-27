Rule Engine using AST by Jyoti Gupta
Overview

This application functions as a rule engine to assess user eligibility based on various attributes, such as age, department, salary, and experience. It utilizes an Abstract Syntax Tree (AST) to represent and manage conditional rules, enabling the dynamic creation, combination, and evaluation of rules.
Features

    Rule Creation: Users can define rules using a string format, which is then transformed into an AST for easy rule management.

    Rule Combination: Supports merging multiple rules into a single AST to perform more complex evaluations.

    Rule Evaluation: Evaluates whether given data aligns with the criteria set by the AST.

    Tree Visualization: Displays a tree representation for better understanding when defining or combining rules.

Tech Stack

    Backend: Built with Node.js and Express.js
    Database: MongoDB for storing rules and evaluations

Getting Started
Prerequisites

    Install Node.js and npm.

Installation Steps

    Clone the Repository:

    bash

git clone "https://github.com/jyotigupta/Rule-Engine-with-AST.git"

Install Backend Dependencies:

bash

npm install

Configure Database:

    Create a .env file and add your MongoDB connection URL:

    plaintext

    MONGO_URL="<your_mongo_db_connection_url>"

Launch the Server:

bash

    npm start

API Endpoints

    Create a Rule
        Endpoint: /api/create_rule
        Method: POST
        Request Body:

        json

    {
      "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
      "ruleName": "Rule-1"
    }

    Note: Ensure proper spacing in the rule string. The rule format should be variable operator value.

Combine Rules

    Endpoint: /api/rules/combine_rules
    Method: POST
    Request Body: Provide rules to be combined.

Evaluate a Rule

    Endpoint: /api/rules/evaluate_rule
    Method: POST
    Request Body:

    json

{
"rule": { ... },
"data": {
"age": 35,
"department": "Sales",
"salary": 60000,
"experience": 3
}
}

Sample Response:

json

        {
          "result": true
        }

Running Tests

To verify functionality, implement and run tests to ensure the application is working as expected.