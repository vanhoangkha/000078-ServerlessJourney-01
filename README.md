# Serverless - Lambda interact with S3 and DynamoDB

> Serverless journey, part 1.

A hands-on workshop from the [AWS First Cloud Journey](https://github.com/vanhoangkha/aws-first-cloud-journey) series, available in English and Vietnamese.

**Read the workshop online:** https://vanhoangkha.github.io/000078-ServerlessJourney-01/

## Overview

This is a series about Serverless. AWS provides technologies for running code, managing data, and integrating applications, all without managing servers. Those technologies serve users to create applications under the Serverless model. Serverless applications start with AWS Lambda, save data with DynamoDB, receive user requests with API Gateway, host static web with S3/AWS Amplify Console, ....

Example of a web application using the Serverless model with the cloud:

## Workshop contents

1. Introduction
2. Resize image
   - Create resize image Lambda function
   - Create S3 bucket
   - Create Policy for Lambda function
   - Test Lambda function operation
3. Write data to DynamoDB
   - Create DynamoDB table
   - Write data by Lambda function
4. Clean up

## Prerequisites

- An AWS account with permissions to create the resources used in the labs
- Basic familiarity with the AWS Management Console
- [Hugo](https://gohugo.io/installation/) (extended edition) if you want to run the site locally

## Run locally

```bash
git clone https://github.com/vanhoangkha/000078-ServerlessJourney-01.git
cd 000078-ServerlessJourney-01
hugo server
```

Then open http://localhost:1313 in your browser.

## Repository structure

| Path | Purpose |
| --- | --- |
| `content/` | Workshop pages (`*.md` English, `*.vi.md` Vietnamese) |
| `static/` | Images and other static assets |
| `layouts/` | Hugo layout overrides |
| `themes/` | Hugo theme |
| `config.toml` | Site configuration |

## Cost and cleanup

The labs create AWS resources that may incur charges. Complete the **Clean up** chapter when you finish to remove them.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

To report a security issue, see [SECURITY.md](SECURITY.md).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
