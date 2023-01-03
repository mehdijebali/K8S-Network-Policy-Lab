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