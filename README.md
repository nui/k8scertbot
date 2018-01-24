# k8scertbot

Easily renew letsencrypt certificate for system running under k8s

## Generate/Renew certificates

1. Change `ingress.yaml` to match you domain name
2. Run on cluster
  - `cd k8s`
  - `kubectl apply -f pod.yaml`
  - `kubectl apply -f service.yaml`
  - `kubectl apply -f ingress.yaml`
3. Execute into container, `kubectl exec -i -t k8scertbot`
4. Generate/Renew certificates, `certbot certonly -w . --cert-name <name> -d host_1,host_2,...,host_n`
