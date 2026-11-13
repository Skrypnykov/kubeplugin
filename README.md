**kubeplugin** is a bash script that extends the functionality of the `kubectl top` command. It allows you to retrieve CPU and memory usage statistics for `pods` and `nodes` of a specified namespace in your K8s cluster.

# Installing kubeplugin

1. **Clone the repository to your local machine.**
```
git clone https://github.com/Skrypnykov/kubeplugin.git
```
2. **Navigate to the directory containing the script.**
```
cd kubeplugin/scripts
```
3. **Make the script executable.**
```
chmod +x kubeplugin
```
4. **Move the script to the directory where other kubectl plugins are located.** (For example, on Unix-like systems, it might be /usr/local/bin/)
```
sudo mv kubeplugin /usr/local/bin/
```
5. **Execute the script with the desired arguments.**
```
kubeplugin <node or pod> <namespace>
```
Replace <node or pod> with the type of resource you want to query (e.g., node or pod), and <namespace> with the namespace you want to query. 

**Example of usage**
```
$ kubeplugin pods kube-system
Resource     Namespace       Name                                          CPU        Memory
pods         kube-system     coredns-559f6c778d-t6cl2                      3m         42Mi  
pods         kube-system     coredns-559f6c778d-z9kw9                      3m         40Mi  
pods         kube-system     etcd-kind-control-plane                       39m        80Mi  
pods         kube-system     kindnet-wv6kx                                 1m         46Mi  
pods         kube-system     kube-apiserver-kind-control-plane             75m        310Mi 
pods         kube-system     kube-controller-manager-kind-control-plane    40m        115Mi 
pods         kube-system     kube-proxy-t2lwr                              2m         55Mi  
pods         kube-system     kube-scheduler-kind-control-plane             15m        68Mi  
pods         kube-system     metrics-server-5d64fb4897-h6k45               3m         17Mi  

```

```
$ kubeplugin node kube-system
Resource     Namespace       Name                                          CPU        Memory
node         kube-system     kind-control-plane                            291m       3%    

```
