## 1. Install microk8s in Ubuntu boxes
https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#5-host-your-first-service-in-kubernetes

## 2. Enable addons
ingress, dashboard
(maybe kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/mandatory.yaml)

## 3. Get the token and access dashboard
```bash
token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s kubectl -n kube-system describe secret $token
```

## 4. deploy services (apple/banana) and Ingress
https://matthewpalmer.net/kubernetes-app-developer/articles/kubernetes-ingress-guide-nginx-example.html

## 5. Test
From host machine, ip address on http and https should load up
http://192.168.0.140/banana
http://192.168.0.140/apple
http://192.168.0.140/


## 6. Build multi node
https://ubuntu.com/tutorials/how-to-kubernetes-cluster-on-raspberry-pi?&_ga=2.240508548.649096280.1632367809-335135294.1631882064#5-master-node-and-leaf-nodes
> Troubleshoot: regenerate the mac address in NIC in parallels

