# notes to pull image from harbor
1. added the file kustomization.yaml in /overlays/harbor, so that container image and imagePullSecrets are pulled from harbor
2. check fluent-bit image existed in https://harbor.services.tkg-lab.k8s.boeing.com/harbor/projects/3/repositories
3. make sure base/kustomization.yaml include - harbor-secret-sealed.yaml
4. 
- alias kf="kubectl -n fluent-bit"
- kf delete -k ../overlays/harbor/
- kf apply -k ../overlays/harbor/
- k -n tanzu-continuousdelivery-resources edit ks-fluent-bit

5. make sure TMC path point to harbor