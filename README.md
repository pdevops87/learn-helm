# learn-helm

to install helm chart:
helm install "release-name" . (here . is a current directory)

helm install demo .

to set through cli :
helm install demo . --set podName=test

values.yaml: this is a default values for all template files like cart.yaml,catalogue.yaml,....
to override default values to new values add another folder , under this folder create templating value
like pass-values(this is a folder) ----> under this cart.yaml,catlogue.yaml(add values)


Helm reads:   helm install demo .
===========
Chart.yaml
values.yaml
files in templates/
It renders these templates into final Kubernetes manifest YAMLs
(these are plain resource definitions like Deployments, Services, etc.)
Then Helm sends those manifests to the Kubernetes API server
The cluster (e.g., Amazon EKS) creates actual resources from them:
Pods
Deployments
Services
etc.



Helm → sends instructions 📦
API Server → records the instructions 🧾
Controllers + Nodes → make it real ⚙️

files: |
{{ .Files.Get "files/sample.conf" | indent 2 }}