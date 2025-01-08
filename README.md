# 2.15_SecretMgmt_Assignment

Answer the following:

1. What is needed to authorize your EC2 to retrieve secrets from the AWS Secret Manager?
- To authorize an Amazon EC2 instance to retrieve secrets from AWS Secrets Manager, we need to assign it an IAM role with an appropriate policy. This policy needs to provide the necessary permissions to allow the EC2 instance to access Secrets Manager and retrieve the secret.


2. Derive the IAM policy (i.e. JSON)?
Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access

- The IAM policy should include the necessary actions like secretsmanager:GetSecretValue, and it should be scoped to only allow access to the specific secret (prod/cart-service/credentials in this case).

- Action: secretsmanager:GetSecretValue – This action allows the EC2 instance to retrieve the value of a secret from Secrets Manager.

- Resource: The resource section uses the ARN (Amazon Resource Name) of the secret that the EC2 instance will access.

- Assuming the secret is in the ap-southeast-1 region and the AWS account ID is 123456789, the sensible ARN for the secret would look like this

- arn:aws:secretsmanager:ap-southeast-1:123456789:secret:prod/cart-service/credentials-*