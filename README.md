# K8s Network Policy 
In this Lab, we will explore the basics of K8s Network Policy Object. 
K8s Network Policies are used to Control the Traffic Flow between pods at IP Address or Port level.
Network policies allow to build a secure network by keeping Pods **isolated from traffic they do not need** because pods are not isolated: They accept traffic from any source by default. In fact, Pods become isolated by having a NetworkPolicy that selects them.
## Network Policy Components
#### podSelector
**podSelector** Determines to which pods in namespace the NetworkPolicy will be applied. We can can select the Pods using **Labels**. note that an empty podSelector selects all pods in the namespace. 
#### Ingress
Incoming Network Trafﬁc coming into the Pod from another Source.
#### Egress
Outgoing Network Trafﬁc that leaving the Pod for another Destination.
#### fromSelector
Selects **Ingress** Trafﬁc that will be allowed on Pods.
#### toSelector
Selects **Egress** Trafﬁc that will be allowed from Pods.

Network policies are specified by using three identifiers:
- Other pods that are allowed
- Namespaces that are allowed
- IP blocks/ Ports
## Instructions
1. Clone the project 
```
git clone https://github.com/mehdijebali/K8s_App_Configuration_Lab.git
```
2. Apply manifest using **kubectl**
```
kubectl apply -f /path/to/manifest.yml
```
3. You can check the status of pods, services, deployments, and ingresses  with the following commands
```
kubecl get pods | grep <pod_name>
kubectl get networkpolicy | grep <network_policy_name>
```
4. You can also list additional information of specifice pod,service, deployment, and ingress for any debugging issue
```
kubectl describe pod <pod_name>
kubectl describe networkpolicy <network_policy_map_name>
```
The **<pod_name>, <network_policy_name>)** are the values of the key `metadata.name` in each k8s manifest yaml file.