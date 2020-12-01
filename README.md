# Welcome to your CDK TypeScript project!

You should explore the contents of this project. It demonstrates a CDK app with an instance of a stack (`CdkEksBlueprintStack`)
which contains an Amazon SQS queue that is subscribed to an Amazon SNS topic.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

 * `npm run build`   compile typescript to js
 * `npm run watch`   watch for changes and compile
 * `npm run test`    perform the jest unit tests
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk synth`       emits the synthesized CloudFormation template
# Bootstrapping
Each combination of target account and region must be boostrapped prior to deploying stacks.
Bootstrapping is an process of creating IAM roles and lambda functions that can execute some of the common CDK constructs.

In addition to the regular [environment bootstrapping](https://docs.aws.amazon.com/cdk/latest/guide/bootstrapping.html) pipeline bootstrapping for pipelines requires a new style of bootstrapping. Execute (with account admin privileges) the command in bootstrap-pipeline.sh.  


# cdk-eks-blueprint
Support context variables (specify in cdk.json, cdk.context.json or pass with -c command line option):

- instanceType: (defaulted to "t3.medium") Type of instance for the EKS cluster, must be a valid instance type like t3.medium
- vpc: Specifies whether to use an existing VPC (if specified) or create a new one if not specified.
- minSize: Min cluster size, must be positive integer greater than 0 (default 1).
- maxSize: Max cluster size, must be greater than minSize.
- vpcSubnets ="List of VPC subnets for cluster provisioning (unsupported yet)


