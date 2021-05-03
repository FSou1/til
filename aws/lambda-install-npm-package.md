# How to use npm packages in AWS Lambda

You cannot load NPM modules without uploading a `.zip` file.

In order to upload a `.zip` file, you need:
* Put a lamda function file in a separate directory
* Install necessary npm package(s)
* Make sure the function works locally with `node lambdaFunc.js`
* Go to the directory and compress the contents ([How to create a Zip archive with CLI](/7z/create-zip-with-cli.md))
* Upload the function package:
```
aws lambda update-function-code --function-name poc --region us-east-2 --zip-file fileb://C:/Projects/git/SeasonedDeveloper/path-to-function/lambdaFunc.zip
```

You mayu need to:
* specify a region with the `--region` parameter
* configure AWS CLI with `aws configure`
  * create a user with AWS Access Key & Secret

References:
* https://stackoverflow.com/a/34439125/2524304
* https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html