# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.


## Description:
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

## Steps
1. Create and EC2 Instance.
2. Create a Snapshot of the EBS volume of the Instance.
** File 1**
** File 2**

**Now in order to delete the snapshots, we will use lambda function**

3. Create a Lmabda function.
** File 3 **
4. Write the Lambda function code.

** File 4 & 5 **

5. Click on deploy and test.
6. Give the test name and save it.

** File 6**

7. Again click on the test, the test will fail due to certain permissions,

** File 7**

8. Now, we will give permissions, but before that go to thr permissions tab and edit and increase the default execution time to 10 sec and save

**File 8 **
** File 9**

9. Click on the permissions, Open the role and add new permissions to it

** File 10**

10. Cretae a policy to attach it to the snapshot.

** File 11 **

