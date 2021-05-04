# How to invoke AWS Lambda at a sub-minute frequency

Unfortunately, there is no simple and straightforward solution for this task.

If you try to use the every 10 seconds cron expression `0/10 0 0 ? * * *`, then you get the `Parameter ScheduleExpression is not valid` error message.

The only workaround is to create a Step Functions State Machine, that invokes another Lambda to track the current number of iterations, which invokes our original Lambda.

![workaround schema](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2018/05/13/architecture_v2small2.png)

References:
* https://aws.amazon.com/blogs/architecture/a-serverless-solution-for-invoking-aws-lambda-at-a-sub-minute-frequency/