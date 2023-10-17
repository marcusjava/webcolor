<h1 align="center">Webcolor Kubernetes Helm Chart </h1>

## 1 - Instalação.

### Helm

Para realizar a instalação do (<a href="https://helm.sh/docs/intro/install/">Helm</a>) basta clicar no link.

### Aplicação.

Altere o arquivo <strong>values.yaml</strong> de acordo com sua necessidade e em seguida execute seguinte comando na raiz da aplicação.

`helm install webcolor -f values.yaml -n webcolor --create-namespace`

#### 2 - Verificando a instalação:

`kubectl get all -n novosga`

```markdown
NAME READY STATUS RESTARTS AGE
pod/novosga-app-deployment-647dfc47bd-5ct59 1/1 Running 0 37m
pod/novosga-db-statefulset-0 1/1 Running 0 37m

NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE
service/app-svc NodePort 10.96.234.63 <none> 80:30000/TCP 37m
service/db-svc ClusterIP None <none> 3306/TCP 37m

NAME READY UP-TO-DATE AVAILABLE AGE
deployment.apps/novosga-app-deployment 1/1 1 1 37m

NAME DESIRED CURRENT READY AGE
replicaset.apps/novosga-app-deployment-647dfc47bd 1 1 1 37m

NAME READY AGE
statefulset.apps/novosga-db-statefulset 1/1 37m
```

#### 3 - Desinstalando chart:

`helm uninstall novosga`

#### 4 - Criando Helm package.

Ex: `helm package novosga --destination ./packages --version 0.1.1`
