# Amazon EKS cluster authentication 

## Cloud side

### Enabling IAM principal access to your cluster (optional)

Upon creating an Amazon EKS cluster, the IAM entity, which can be a user or role responsible for the cluster's creation, is automatically granted administrative privileges within the Kubernetes RBAC authorization table. As a result, only this IAM user initially possesses the necessary permissions to interact with the Kubernetes API server through kubectl.

To provide an IAM user access to an Amazon EKS cluster by updating the aws-auth ConfigMap, follow these steps:
* Create the **aws-auth-config-map.yaml** file
    ```
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: aws-auth
      namespace: kube-system
    data:
      mapUsers: |
        - userarn: arn:aws:iam::<account_id>:user/<username>
          username: <username>
          groups:
            - system:masters
    ```
* Apply the updated aws-auth ConfigMap
```
kubectl apply -f aws-auth-config-map.yaml
```

If you are exploring alternative methods to enable IAM principal access to your cluster, consider the following options:
```
https://docs.aws.amazon.com/eks/latest/userguide/add-user-role.html
```