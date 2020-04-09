# tech-nugget-gcloud-shell
Quick Reference - Useful commands
_For now, all here, in the future I will lay it out based on topic_

**SSH to the GCP shell**
_Requires alpha to be installed_ <br />
` gcloud alpha cloud-shell ssh`


**Create a Container Cluster Example** <br />
`gcloud container clusters create my-ultimate-cluster \ 
--num-nodes=3 --machine-type=e2-small --zone=us-west2-a \ 
--issue-client-certificate --enable-basic-auth`

 

