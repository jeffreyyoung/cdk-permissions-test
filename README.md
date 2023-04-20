# Welcome to your CDK TypeScript project

This is a blank project for CDK development with TypeScript.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template

```
Andreas-MacBook-Pro:cdk-permissions-test jeffrey$ cdk deploy --profile dev

✨  Synthesis time: 8.99s

CdkPermissionsTestStack: building assets...

[0%] start: Building 9100e1f25e3613f6f3b64a9296d685424ff6fed8f1be71e22df56e21c1c88d81:current_account-current_region
[0%] start: Building de91205450df70f943fbde8ad6f4eec685d4c82c11ddec668199a8d2ec4d7065:current_account-current_region
[0%] start: Building 31d4d47c63e5639ceadc558c2f174fbe15e43592280938d0576d5821784c5f2d:current_account-current_region
[0%] start: Building f2465695658ba037e48801c9f75049e61633e3e9f6ff2c53ae1c703cd7d5a3d8:current_account-current_region
[25%] success: Built 9100e1f25e3613f6f3b64a9296d685424ff6fed8f1be71e22df56e21c1c88d81:current_account-current_region
[50%] success: Built de91205450df70f943fbde8ad6f4eec685d4c82c11ddec668199a8d2ec4d7065:current_account-current_region
[75%] success: Built 31d4d47c63e5639ceadc558c2f174fbe15e43592280938d0576d5821784c5f2d:current_account-current_region
[100%] success: Built f2465695658ba037e48801c9f75049e61633e3e9f6ff2c53ae1c703cd7d5a3d8:current_account-current_region

CdkPermissionsTestStack: assets built

This deployment will make potentially sensitive changes according to your current security approval level (--require-approval broadening).
Please confirm you intend to make the following modifications:

IAM Statement Changes
┌───┬────────────────────┬────────┬────────────────────┬──────────────────────┬───────────┐
│   │ Resource           │ Effect │ Action             │ Principal            │ Condition │
├───┼────────────────────┼────────┼────────────────────┼──────────────────────┼───────────┤
│ + │ ${Custom::CDKBucke │ Allow  │ sts:AssumeRole     │ Service:lambda.amazo │           │
│   │ tDeployment8693BB6 │        │                    │ naws.com             │           │
│   │ 4968944B69AAFB0CC9 │        │                    │                      │           │
│   │ EB8756C/ServiceRol │        │                    │                      │           │
│   │ e.Arn}             │        │                    │                      │           │
├───┼────────────────────┼────────┼────────────────────┼──────────────────────┼───────────┤
│ + │ ${WebsiteBucket.Ar │ Allow  │ s3:Abort*          │ AWS:${Custom::CDKBuc │           │
│   │ n}                 │        │ s3:DeleteObject*   │ ketDeployment8693BB6 │           │
│   │ ${WebsiteBucket.Ar │        │ s3:GetBucket*      │ 4968944B69AAFB0CC9EB │           │
│   │ n}/*               │        │ s3:GetObject*      │ 8756C/ServiceRole}   │           │
│   │                    │        │ s3:List*           │                      │           │
│   │                    │        │ s3:PutObject       │                      │           │
│   │                    │        │ s3:PutObjectLegalH │                      │           │
│   │                    │        │ old                │                      │           │
│   │                    │        │ s3:PutObjectRetent │                      │           │
│   │                    │        │ ion                │                      │           │
│   │                    │        │ s3:PutObjectTaggin │                      │           │
│   │                    │        │ g                  │                      │           │
│   │                    │        │ s3:PutObjectVersio │                      │           │
│   │                    │        │ nTagging           │                      │           │
├───┼────────────────────┼────────┼────────────────────┼──────────────────────┼───────────┤
│ + │ ${WebsiteBucket.Ar │ Allow  │ s3:GetObject       │ AWS:*                │           │
│   │ n}/*               │        │                    │                      │           │
├───┼────────────────────┼────────┼────────────────────┼──────────────────────┼───────────┤
│ + │ arn:${AWS::Partiti │ Allow  │ s3:GetBucket*      │ AWS:${Custom::CDKBuc │           │
│   │ on}:s3:::{"Fn::Sub │        │ s3:GetObject*      │ ketDeployment8693BB6 │           │
│   │ ":"cdk-hnb659fds-a │        │ s3:List*           │ 4968944B69AAFB0CC9EB │           │
│   │ ssets-${AWS::Accou │        │                    │ 8756C/ServiceRole}   │           │
│   │ ntId}-${AWS::Regio │        │                    │                      │           │
│   │ n}"}               │        │                    │                      │           │
│   │ arn:${AWS::Partiti │        │                    │                      │           │
│   │ on}:s3:::{"Fn::Sub │        │                    │                      │           │
│   │ ":"cdk-hnb659fds-a │        │                    │                      │           │
│   │ ssets-${AWS::Accou │        │                    │                      │           │
│   │ ntId}-${AWS::Regio │        │                    │                      │           │
│   │ n}"}/*             │        │                    │                      │           │
└───┴────────────────────┴────────┴────────────────────┴──────────────────────┴───────────┘
IAM Policy Changes
┌───┬──────────────────────────────────────────┬──────────────────────────────────────────┐
│   │ Resource                                 │ Managed Policy ARN                       │
├───┼──────────────────────────────────────────┼──────────────────────────────────────────┤
│ + │ ${Custom::CDKBucketDeployment8693BB64968 │ arn:${AWS::Partition}:iam::aws:policy/se │
│   │ 944B69AAFB0CC9EB8756C/ServiceRole}       │ rvice-role/AWSLambdaBasicExecutionRole   │
└───┴──────────────────────────────────────────┴──────────────────────────────────────────┘
(NOTE: There may be security-related changes not in this list. See https://github.com/aws/aws-cdk/issues/1299)

Do you wish to deploy these changes (y/n)? y
CdkPermissionsTestStack: deploying... [1/1]
[0%] start: Publishing 9100e1f25e3613f6f3b64a9296d685424ff6fed8f1be71e22df56e21c1c88d81:current_account-current_region
[0%] start: Publishing de91205450df70f943fbde8ad6f4eec685d4c82c11ddec668199a8d2ec4d7065:current_account-current_region
[0%] start: Publishing 31d4d47c63e5639ceadc558c2f174fbe15e43592280938d0576d5821784c5f2d:current_account-current_region
[0%] start: Publishing f2465695658ba037e48801c9f75049e61633e3e9f6ff2c53ae1c703cd7d5a3d8:current_account-current_region
[25%] success: Published 9100e1f25e3613f6f3b64a9296d685424ff6fed8f1be71e22df56e21c1c88d81:current_account-current_region
[50%] success: Published de91205450df70f943fbde8ad6f4eec685d4c82c11ddec668199a8d2ec4d7065:current_account-current_region
[75%] success: Published 31d4d47c63e5639ceadc558c2f174fbe15e43592280938d0576d5821784c5f2d:current_account-current_region
[100%] success: Published f2465695658ba037e48801c9f75049e61633e3e9f6ff2c53ae1c703cd7d5a3d8:current_account-current_region
CdkPermissionsTestStack: creating CloudFormation changeset...
[█████████████████▍········································] (3/10)

5:13:41 PM | CREATE_FAILED        | AWS::S3::BucketPolicy         | WebsiteBucket/Policy
API: s3:PutBucketPolicy Access Denied
5:13:43 PM | ROLLBACK_IN_PROGRESS | AWS::CloudFormation::Stack    | CdkPermissionsTestStack
The following resource(s) failed to create: [WebsiteBucketPolicyE10E3262, CustomCDKBucketDeployment8693BB6
4968944B69AAFB0CC9EB8756CServiceRoleDefaultPolicy88902FDF, Distribution830FAC52]. Rollback reque
5:13:41 PM | CREATE_FAILED        | AWS::S3::Bu
cketPolicy         | WebsiteBucketPolicyE10E326
2
API: s3:PutBucketPolicy Access Denied


 ❌  CdkPermissionsTestStack failed: Error: The stack named CdkPermissionsTestStack failed creation, it may need to be manually deleted from the AWS console: ROLLBACK_COMPLETE: API: s3:PutBucketPolicy Access Denied
    at FullCloudFormationDeployment.monitorDeployment (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:380:10236)
    at runMicrotasks (<anonymous>)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
    at async deployStack2 (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:383:145458)
    at async /Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:383:128776
    at async run (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:383:126782)

 ❌ Deployment failed: Error: Stack Deployments Failed: Error: The stack named CdkPermissionsTestStack failed creation, it may need to be manually deleted from the AWS console: ROLLBACK_COMPLETE: API: s3:PutBucketPolicy Access Denied
    at deployStacks (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:383:129083)
    at runMicrotasks (<anonymous>)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
    at async CdkToolkit.deploy (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:383:147507)
    at async exec4 (/Users/jeffrey/.nvm/versions/node/v16.18.0/lib/node_modules/aws-cdk/lib/index.js:438:51799)

Stack Deployments Failed: Error: The stack named CdkPermissionsTestStack failed creation, it may need to be manually deleted from the AWS console: ROLLBACK_COMPLETE: API: s3:PutBucketPolicy Access Denied
```