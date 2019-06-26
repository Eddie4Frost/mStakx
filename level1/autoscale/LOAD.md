#Execute the following command in other terminal  
kubectl run -i --tty load-generator --image=busybox /bin/sh -n "staging/production"

#Execute the command according the namespace
while true; do wget -q -O- http://frontend.staging.svc.cluster.local; done
while true; do wget -q -O- http://frontend.production.svc.cluster.local; done
