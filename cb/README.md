# Part 1 - Create a simple Nginx app

1. Create a new namespace

```
# kubectl create namespace istio-examples
# kubectl label namespace istio-examples istio-injection=enabled
```

2. Deploy a simple nginx example

```
# kubectl apply -f nginx.yml -n istio-examples
```

3. Verify nginx app is working

Run `minikube service` command to find out the URL of nginx app.  You should see a web page with 'Welcome to nginx'.

```
# minikube service nginx --url -n istio-examples
> http://192.168.39.43:30080   # Open this URL in the browser
```

---

# Part 2 - Introduce Isito Service Mesh

1. Create a traffic routing via Ingress gateway
```
# kubectl apply -f istio.yml -n istio-examples
```

