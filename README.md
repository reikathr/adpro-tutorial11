# adpro-tutorial11

1. Compare the application logs before and after you exposed it as a Service.
Before the application was exposed as a service, the application logs didn't have anything but messages saying that it's started the servers. Afterwards, it shows that several GET requests were made to the application.

2. Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to kube-system. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?
`-n` stands for namespace. Namespaces in kubernetes provide a mechanism for isolating groups of resources in a single cluster, which is useful when you have environments with many users used by many teams and many projects. Without the `-n`, the output will list the pods and services I've created explicitly in the default namespace. With the `-n kube-system` the command is asking to list the pods and services in the kube-system namespace specifically. The kube-system namespace is the namespace for objects created by Kubernetes.