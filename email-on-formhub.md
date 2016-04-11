# Setting up email on formhub on amazon

Follow the directions [Here] (https://github.com/SEL-Columbia/formhub/wiki/How-To-Run-Your-Own-Formhub-Instances-on-Amazon-Web-Services)

Everything is straight forward except for the setting up Amazon SES (its email service) so this is meant to help with that.

1. In AWS console go to Identity and Access Management, create a IAM user and attache the policy *AmazonSESFullAccess* Make note of the access and secret id
2. Go to the SES console create one email address with a Policy that sets the IAM user created above as its principle. Ensure that bothe SendEmail and SendRawEmail are included actions to the policy. 
3. Amazon requires you to list the chosen iam user ARN which you can get from the user summary in the identity and access management console
4. It is not necessary to set up SMTP in Amazon SES. SES uses a client boto which only needs a access_key and secret_key of an IAM profile
