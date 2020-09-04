### EFS to EFS Datasync solution.
Note that main solution is extracted from https://github.com/aws-samples/amazon-efs-tutorial/tree/master/in-cloud-transfer
But in original solution I found some short comings in automation and cost effectiveness which I included in my solution.

1. In original solution synchronization runs for schedule but EC2 agent keeps running and no automation provided to stop and start agent. Which I included here using an scheduled CloudWatch Event and lambda.
2. Datasync service logging was not provided which I added here to pass it to cloud watch logs.
3. When stack is deleted the datasync resources created in destination region remains. Here I wrote a second template to take care of that as well.
