# KubernetesProject
sudo systemctl enable docker
sudo systemctl start docker
kubectl run mynginx --image=nginx
kubectl get pods
kubectl run my-nginx --image=nginx123
kubectl describe pod my-nginx
![image](https://github.com/user-attachments/assets/b4df91e3-ef0f-4305-9bfe-3b09f9213cc7) # the photo shows error in the image pulling as nginx123 image doesn't exist
kubectl get pod mynginx -o wide
kubectl delete pod mynginx
kubectl apply -f pod.yaml
kubectl get pods --show-labels
kubectl apply -f replicaset.yaml
kubectl get rs
kubectl get pods
<img width="469" alt="image" src="https://github.com/user-attachments/assets/f7e2905d-d789-49d4-aa5b-39f4e99399af" /> # the image shows the successful applying of the replicaset
kubectl scale rs nginx-rs --replicas=5
![image](https://github.com/user-attachments/assets/4d957262-d053-4424-bdaa-aa52adf5f31c) # image shows the successful scaling of the pod into 5 replicas
After deleting a pod the system automatically creates another one
kubectl edit rs nginx-rs
kubectl get pods
![image](https://github.com/user-attachments/assets/4af3e823-f77b-42cb-8a29-7007aa4004e2) # image shows successful scale down of the pods
kubectl get deployment deployment-1 -o=jsonpath="{.spec.template.spec.containers[*].image}" # command used to know what Image name that running the deployment 
kubectl apply -f httpd.yaml
kubectl get pods
<img width="611" alt="image" src="https://github.com/user-attachments/assets/57ad1923-42cb-4677-b104-8152559e8449" /> # The image shows the successful creation of the deployment
kubectl set image deployment/httpd-frontend httpd-container=nginx777
kubectl rollout status deployment/httpd-frontend
kubectl get deployment httpd-frontend -o=jsonpath="{.spec.template.spec.containers[*].image}"
<img width="829" alt="image" src="https://github.com/user-attachments/assets/3139d67f-5d40-4e46-b563-d501abfaff77" /> # The image shows the successful update of the image 
kubectl rollout undo deployment/httpd-frontend
kubectl rollout status deployment/httpd-frontend
kubectl get deployment httpd-frontend -o=jsonpath="{.spec.template.spec.containers[*].image}"
kubectl apply -f dockerhub.yaml
kubectl get pods 
<img width="604" alt="image" src="https://github.com/user-attachments/assets/ac4c94aa-76e3-43cd-b7ad-457c2d121632" /> # The following image shows the successful pulling of the image from dockerhub
kubectl apply -f service.yaml
<img width="565" alt="image" src="https://github.com/user-attachments/assets/e1554bdc-dced-4c41-ba86-aa6996a2fc7a" /> # The following image shows the successful creation of the service










