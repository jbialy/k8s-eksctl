# k8s-eksctl

Using [`eksctl`](https://github.com/weaveworks/eksctl) to deploy an EKS cluster.

Install `aws-iam-authenticator`:

```
go get -u -v github.com/kubernetes-sigs/aws-iam-authenticator/cmd/aws-iam-authenticator

```

and `eksctl`:

```
brew install eksctl
```

Deploy to `us-east-1`:

```
$ eksctl create cluster --region us-east-1 --zones=us-east-1b,us-east-1c,us-east-1d --node-type=t2.medium --auto-kubeconfig
```

> There's a problem deploying to **us-east-1e** hence the need to explicitly define the AZs. By default, the above will create a two node cluster.

Delete:

```
$ eksctl delete cluster --name=scrumptious-sheepdog-1536846573
```

