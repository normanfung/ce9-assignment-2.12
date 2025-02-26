# CE9-Assignment-2.12
AWS Lambda


### What is the purpose of the execution role on the Lambda function?
The lambda function receives permissions to access AWS resources from its execution role.
The default execution role that the Lambda console creates only has permission to store logs in Amazon CloudWatch Logs.

### What is the purpose of the resource-based policy on the Lambda function?
AWS services and other AWS accounts receive permissions to invoke your function from their resource-based policy. 
Resource-based policies enable you to grant usage permissions to other accounts on a per-resource basis. 
You use a resource-based policy to allow an AWS service to invoke your function.

## If the function is needed to upload a file into an S3 bucket, describe (i.e no need for the actual policies).
### What is the needed update on the execution role? 
To allow the Lambda function to upload a file into an S3 bucket, the execution role for the Lambda function needs to have permissions to write to the S3 bucket. Specifically,we have to add permissions for the s3:PutObject action on the target S3 bucket.


### What is the new resource-based policy that needs to be added (if any)?
If S3 is being used to trigger the Lambda function (for example, when an object is uploaded to the bucket), the new resource-based policy must be added to the Lambda function to allow S3 to invoke it.The Principal in the policy would be the s3.amazonaws.com, and the SourceArn would specify the S3 bucket that can trigger the Lambda function.
