# kubectl create -f pod-emptydir.yaml

# kubectl get pod

# kubectl exec -ti busybox -c busy -- touch /giropops/funciona

# kubectl exec -ti busybox -c busy -- ls -l /giropops/

# kubectl get pod -o wide

# find /var/lib/kubelet/pods/ -iname giropops-dir

# ls /var/lib/kubelet/pods/7d...kubernetes.io~empty-dir/giropops-dir

# kubectl delete -f pod-emptydir.yaml

# ls /var/lib/kubelet/pods/7d...kubernetes.io~empty-dir/giropops-dir



# apt-get install nfs-kernel-server -y

# sudo yum install nfs-utils -y

# apt-get install -y nfs-common

# mkdir /opt/giropops

# chmod 1777 /opt/giropops/

# vim /etc/exports
/opt/giropops *(rw,sync,no_root_squash,subtree_check)

# exportfs -ra

# touch /opt/giropops/FUNCIONA



# kubectl create -f primeiro-pv.yaml

# kubectl get pv

# kubectl describe pv primeiro-pv




# kubectl create -f primeiro-pvc.yaml

# kubectl get pv

# kubectl get pvc



# kubectl create -f nfs-pv.yaml

# kubectl describe deployment nginx

# kubectl get pods -o wide

# kubectl describe pod nginx-b4bd77674-gwc9k

# kubectl exec -ti nginx-b4bd77674-gwc9k -- ls /giropops/

# kubectl exec -ti nginx-b4bd77674-gwc9k -- touch /giropops/STRIGUS

# kubectl exec -ti nginx-b4bd77674-gwc9k -- ls -la  /giropops/

# ls -la /opt/giropops/

# kubectl get deployment

# kubectl delete deployment nginx

# ls -la /opt/giropops/


# cronjobsss

# kubectl create -f primeiro-cron.yaml

# kubectl get cronjobs

# kubectl describe cronjobs.batch giropops-cron

# kubectl get jobs --watch

# kubectl get cronjob giropops-cron

# kubectl get pods

# kubectl  logs giropops-cron-1534979940-vcwdg

# kubectl get pods

# kubectl delete cronjob giropops-cron

# secrets


# echo -n "descomplicando-k8s" > secret.txt

# kubectl create secret generic my-secret --from-file=secret.txt

# kubectl describe secret my-secret

# kubectl get secret

# kubectl get secret my-secret -o yaml

# echo 'ZGVzY29tcGxpY2FuZG8tazhz' | base64 --decode

# kubectl create -f pod-secret.yaml

# kubectl exec -ti teste-secret -- ls /tmp/giropops

# kubectl exec -ti teste-secret -- cat /tmp/giropops/secret.txt

# kubectl create secret generic my-literal-secret --from-literal user=linuxtips --from-literal password=catota

# kubectl describe secret my-literal-secret

# kubectl create -f pod-secret-env.yaml

# kubectl exec teste-secret-env -c busy-secret-env -it -- printenv

configmaps

# mkdir frutas

# echo amarela > frutas/banana

# echo vermelho > frutas/morango

# echo verde > frutas/limao

# echo "verde e vermelha" > frutas/melancia

# echo kiwi > predileta

# git clone https://bitbucket.org/gcalcette/book-descomplicando-k8s.git

# kubectl create configmap cores-frutas --from-literal=uva=roxa --from-file=predileta --from-file=frutas/

# kubectl get configmap




