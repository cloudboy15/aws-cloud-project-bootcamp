## Guidelines: SDK — CDK

|               | AWS SDK                                           | AWS CDK                                                    |
|---------------|---------------------------------------------------|------------------------------------------------------------|
| Programming   | Node.js, Java, Python, Ruby, .NET, etc | TypeScript, JavaScript, Python, Java, C#, Go |
| Abstraction   | Low-level API for configuring and managing resources | Higher-level abstraction that allows you to define resources using code |
| Deployment    | Does not provide built-in deployment capabilities   | Provides a deployment framework using AWS CloudFormation    |


**Quick Launch CDK**

- Write your code
- Check for errors w/ `cdk synth`

**Init AWS CDK running**

```
cdk bootstrap aws://<AWSID>/<AWSREGION>"
```

This will create

- S3 bucket e.g. `cdk-hnb659fds-assets-<AWSID>-<AWSREGION>`
- CFN Toolkit for CDK e.g. CDKToolkit
- ECR Repo

```SH

export UPLOADS_BUCKET_NAME=yaya-cruddur-uploaded-avatars
gp env UPLOADS_BUCKET_NAME=yaya-cruddur-uploaded-avatars
```

[**Provision with AWS CDK**](lib/README.md)


```sh
npm install aws-cdk -g
```

```sh
cdk init app -language typescript
```


```sh
cdk synth
```

```sh
cdk bootstrap "aws://598485450821/ca-central-1"

aws s3api wait bucket-exists \
    --bucket assets.yacrud.me
```

```sh
cdk deploy
```
[**Developer Guide**](../aws/lambdas/process-images/README.md)


### Welcome to your CDK TypeScript project


This is a blank project for CDK development with TypeScript.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template
