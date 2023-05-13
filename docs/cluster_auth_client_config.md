# Amazon EKS cluster authentication 

## Client side

### Install the AWS CLI

<a href="https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html" target="_blank">https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html </a>

### Configure the AWS CLI


```
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

See the details:

<a href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-configure-files-methods" target="_blank">https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-configure-files-methods </a>

If you are exploring alternative methods to configure the AWS CLI, consider the following options:


<a href="https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html" target="_blank">https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html </a>


### Install kubectl

<a href="https://kubernetes.io/docs/tasks/tools/#kubectl" target="_blank">https://kubernetes.io/docs/tasks/tools/#kubectl </a>

### Configure kubectl for the IAM user:
To enable the IAM user to interact with the EKS cluster using kubectl, they will need to configure their local kubectl setup with the cluster's information. Share the following command with the user, replacing CLUSTER_NAME and REGION with the appropriate values:

```
aws eks update-kubeconfig --region <region> --name <cluster_name>
```

If you are exploring alternative methods to configure **kubeconfig** file for an Amazon EKS cluster, consider the following options:

<a href="https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html" target="_blank">https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html </a>