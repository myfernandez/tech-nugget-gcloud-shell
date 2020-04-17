# tech-nugget-gcloud-shell
Quick Reference - Useful commands <br />
_For now, all here, in the future I will lay it out based on topic_

**SSH to the GCP shell**
_Requires alpha to be installed_ <br />
` gcloud alpha cloud-shell ssh`

**Listing zones**
`gcloud compute zones list `

**Create a Container Cluster Example** <br />
`gcloud container clusters create my-ultimate-cluster \  
--num-nodes=3 --machine-type=e2-small --zone=us-west2-a \ 
--issue-client-certificate --enable-basic-auth` 
_Note 1: this command enables node autorepair_ 
_Note 2: kubectl config gets automatically set (see below)_ <br />

**Resize cluster** <br />
`gcloud container clusters resize my-ultimate-cluster --num-nodes <num_nodes>`

###### Kubectl
The full cheatsheet is here:
https://kubernetes.io/docs/reference/kubectl/cheatsheet/
So adding some specific things here:

**Kubectl config** <br />
When creating a cluster through the gcloud cli, the config gets written here: <br />
~/.kube/config
`kubectl config view`
Same does not happen when spinning up a cluster with Terraform
=======
`gcloud container clusters create my-ultimate-cluster\  
--num-nodes=3 --machine-type=e2-small --zone=us-west2-a\  
--issue-client-certificate --enable-basic-auth`

 
**Collecting Pod data with kubectl <br />
`kubectl get pod -o json` <br />
` kubectl get pods -o=jsonpath="{.items[0].status.hostIP}"` <br />
_in that case items[0] is a dictionary, same for status_ <br />
`kubectl describe pod <pod_name>` <br />
_kubectl describe does not support output formatting_ <br />


