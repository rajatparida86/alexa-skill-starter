# Alexa-skill-starter
Starter for learning Alexa skill developments

## Deploy lambda from local

### Create a  s3 bucket
`aws s3 mb s3://test-rajat-lambda-bucket`

### Package your lambda applictiton
```
sam package \
   --template-file example.yaml \
   --output-template-file serverless-output.yaml \
   --s3-bucket test-rajat-lambda-bucket
```

### Deploy the package -- Creates a AWSCloudFormationStack
```
sam deploy \
   --template-file serverless-output.yaml \
   --stack-name test-lambda-stack \
   --capabilities CAPABILITY_IAM
```

### Verify deployment
- Check AWS console for new AWSCloudFormation stack
- Check AWS console for new lambda function

