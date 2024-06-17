#### Traffic Routing: With Ingress, you can conditionally route traffic to one or more services based on specific URL paths, host names, or HTTP headers.

#### SSL/TLS Termination: Using an Ingress controller, you can centrally manage and terminate SSL/TLS certificates, relieving individual services from handling SSL/TLS.

#### Host-based Routing: Traffic can be routed to different services based on various domain names.

#### Path-based Routing: It offers the capability to route traffic to specific services based on URL paths.

#### Efficient Resource Utilization: Multiple services can share the same IP address and port, leading to improved resource efficiency.

#### Scalability: Ingress controllers allow you to extend or customize features such as traffic load balancing, SSL termination, and more.

#### Authentication and Authorization: Some Ingress controllers offer additional security features such as basic authentication, OAuth, or JWT-based authentication.

#### Third-party Integration: Ingress can integrate with popular load balancers like Nginx, Traefik, HAProxy, and many others.

#### External Traffic Monitoring: It can integrate with monitoring solutions to gain insights into traffic patterns, response times, errors, etc.

#### Custom Resources: Some Ingress controllers offer Custom Resource Definitions (CRDs) for more granular traffic management capabilities.

### How to run

#### 1. Create deployment.yml.
```
kubectl create -f kubernetes/template/deployment.yml
```

#### 2. Install the Ingress Controller using Helm.
```
// Install Helm
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 > get_helm.sh
chmod 700 get_helm.sh
./get_helm.sh

// Configure Helm repositories
helm repo add stable https://charts.helm.sh/stable
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
kubectl create namespace ingress-basic

// Install Ingress Controller
helm install nginx-ingress ingress-nginx/ingress-nginx --namespace=ingress-basic
```

#### 3. Verify the installation.
```
kubectl get all --namespace=ingress-basic
```
