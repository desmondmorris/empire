# Empire :: Troubleshooting
 
1. [Overview](./index.md)
2. [Installing](./installing.md)
3. [Using](./using.md)
4. [Administering](./administering.md) **TODO**
5. [Troubleshooting](./troubleshooting.md) **TODO**
6. [Roadmap](./roadmap.md) **TODO**

### Deleting an Empire CloudFormation stack

If you've created an Empire CloudFormation stack and deployed an app to it, you have created an ECS Service with an attached ELB inside the VPC of your Empire stack. Before you can delete the stack, you must no longer have any services or ELBs running inside of it. You can do this by running `emp destroy <app>` for each app in your Empire cluster.

Alternatively, you can [manually delete them][deletingaservice] in the Amazon console. After that, make sure you've deleted the ELB associated with the service as well. Once all dependent ECS Services and ELBs have removed from the VPC of Empire stack, you should be able to delete the stack from the CloudFormation console.

[deletingaservice]: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/delete-service.html
