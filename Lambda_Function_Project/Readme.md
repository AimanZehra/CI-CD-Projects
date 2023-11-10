# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.


## Description:
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

## Steps
1. Create and EC2 Instance.
2. Create a Snapshot of the EBS volume of the Instance.
https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%201.JPG
https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%202.JPG

**Now in order to delete the snapshots, we will use lambda function**

3. Create a Lmabda function.
https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%203.JPG
4. Write the Lambda function code.

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%204.JPG
https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%205.JPG

5. Click on deploy and test.
6. Give the test name and save it.

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%206.JPG

7. Again click on the test, the test will fail due to certain permissions,

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%207.JPG

8. Now, we will give permissions, but before that go to thr permissions tab and edit and increase the default execution time to 10 sec and save

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%208.JPG
https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%209.JPG

9. Click on the permissions, Open the role and add new permissions to it

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%2010.JPG

10. Cretae a policy to attach it to the snapshot.

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%2011.JPG

11. While creating the policy add the delete and other specific permissions, add resource as 'All'

https://github.com/AimanZehra/CI-CD-Projects/blob/main/Lambda_Function_Project/Files/File%2013.JPG

12. Again go back to the role and atach the policy which is just created above.
13. Grant the EC2 full acess as well.
14. Now we will execute the script and we will notice that the snapshot is yet not deleted because the ec2 instance and volume is associated to it.
15. Once we will delte the ec2 instance and run the script again, the snapshot will be delete.


YAY!!
