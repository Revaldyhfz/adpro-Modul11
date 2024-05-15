# Modul 11

## Reflection 1

1. Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?

- When I open the application, each interaction generates a log entry indicating an HTTP GET request. The number of log entries doubles with each new opening of the app, reflecting direct user engagement with the application.

2. Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to kube-system. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

- The -n option in the kubectl get command is used to specify a particular namespace to display resources from. When we use `-n` followed by a namespace like kube-system, it filters the output to show only the resources in that namespace. If the pods or services we created weren't listed when running kubectl get without the `-n` option, it's because they reside in a different namespace than the default one, and we need to use the `-n` option with the appropriate namespace to see them.

## Reflection 2

1. What is the difference between Rolling Update and Recreate deployment strategy?

- A Rolling Update deployment strategy gradually replaces old pods with new ones. It ensures minimal downtime by creating new pods and incrementally removing the old ones. In contrast, the Recreate deployment strategy stops all existing pods before starting the new ones, leading to a complete service interruption during the transition period.

4. What do you think are the benefits of using Kubernetes manifest files? Recall your experience in deploying the app manually and compare it to your experience when deploying the same app by applying the manifest files (i.e., invoking `kubectl apply -f command`) to the cluster.

- Using Kubernetes manifest files has several advantages over manual deployment. These files offer a declarative approach to configuration, specifying the desired state of resources in a clear and consistent manner. This improves reproducibility and reduces the likelihood of errors. Additionally, storing manifest files in version control allows for easy tracking of changes, facilitates collaboration, and simplifies rollback processes if needed. The `kubectl apply -f` command automates the deployment process, ensuring consistency and minimizing manual effort, making the overall deployment more efficient and reliable.