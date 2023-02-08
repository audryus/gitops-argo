```sh
kubectl create configmap stress-test --from-file test.js
kubectl apply -f k6-custom-test.yaml
```