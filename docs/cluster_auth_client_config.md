# Amazon EKS cluster authentication 

## Client side

### Install the AWS CLI

```
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
```

### Configure the AWS CLI


```
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

See the details:

```
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-configure-files-methods
```

If you are exploring alternative methods to configure the AWS CLI, consider the following options:

```
https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html
```

### Install kubectl

```
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
```

### Configure kubectl for the IAM user:
To enable the IAM user to interact with the EKS cluster using kubectl, they will need to configure their local kubectl setup with the cluster's information. Share the following command with the user, replacing CLUSTER_NAME and REGION with the appropriate values:

```
aws eks update-kubeconfig --region REGION --name CLUSTER_NAME
```

If you are exploring alternative methods to configure **kubeconfig** file for an Amazon EKS cluster, consider the following options:

```
https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html
```