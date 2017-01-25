# aws-async-lambda-example

Example CloudFormation stack with an API Gateway method that invokes a Lambda function asynchronously.

# Useful commands

## Deploy stack
To deploy via `aws-cli`:

    aws cloudformation create-stack --stack-name aws-async-lambda-example --capabilities CAPABILITY_NAMED_IAM --template-body file://cfn-template.yaml

## Drilling down
To get the resulting method configuration, first you need the REST API ID (`id` field):

    aws apigateway get-rest-apis

Then, you also need the resource ID (`id` field)

    aws apigateway get-resources --rest-api-id <REST API ID>

Finally, with both those IDs, you could retrieve the method description:

    aws apigateway get-method --rest-api-id <REST API ID> --resource-id <resource ID> --http-method POST
