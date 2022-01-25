# k8s-blue-green / Canary deployment deployment with docker images
* this project is based on (https://github.com/vamsijakkula/canary)
* first the update with built in rolling update feature, by pushing and pulling images on docker hub the pod can switch between new and old versions
* then running old and new version of pods at the same time by configureing load  balancer to manage traffic between to version to make 0 downtime 
* kubectl patch service hello-whale-svc -p '{"spec": {"selector" :{"version": "green"}}}' use this command to directly switch betweeen green and blue version
* to make a detailed load configration ex 50% for old version and 50% for new version, Istio is a common tool to help with this task.
* however Istio's hardware requirements on local minikube is above my current working machine, i will come back to this challenge after I installed duel boot system on my home desktop pc
