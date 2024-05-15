# Modul 11

## Reflection 1

1. Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?

- When I open the application, each interaction generates a log entry indicating an HTTP GET request. The number of log entries doubles with each new opening of the app, reflecting direct user engagement with the application.

2. Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has -n option with value set to kube-system. What is the purpose of the -n option and why did the output not list the pods/services that you explicitly created?

- The -n option in the kubectl get command is used to specify a particular namespace to display resources from. When we use -n followed by a namespace like kube-system, it filters the output to show only the resources in that namespace. If the pods or services we created weren't listed when running kubectl get without the -n option, it's because they reside in a different namespace than the default one, and we need to use the -n option with the appropriate namespace to see them.

