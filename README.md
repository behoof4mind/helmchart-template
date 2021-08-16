# Helm chart repository template

This is template project with auto-versioning and CI inside. Can be used for any new helm chart project.

# Why
This project is a part of fully-automated CI/CD process concept, based on GitOps with ArgoCD

## Prerequisites
1. Make new GitHub repository from this template
2. Clone it
3. Replace/Put Environment Variables
   ```yaml
    # Example values
    ACR_NAME: iitsc
    ACR_USER_NAME: iits-releaser
    SLACK_CHANNEL_ID: "C02AJKXC8UT"
   ```
4. Create new branch, commit and push your first changes
### K8S

Get a K8S cluster. For example see https://minikube.sigs.k8s.io/docs/start/

### Helm

Get Helm : https://helm.sh/docs/intro/install/

## Install

1. Clone the repo
2. cd into ./k8s/helm/workadventure
3. Install workadventure in tag defined in [Chart](./Chart.yml) :
```
helm install myrelease .
```
4. Wait a few seconds for all pods to start
5. With self-signed TLS certificates, make them trust by your browser by going to https://maps.workadventure.minikube/, https://pusher.workadventure.minikube/
6. Then you can start by going to https://play.workadventure.minikube/


By default, Workadventure will respond to https://[play | maps | pusher | uploader | api].workadventure.minikube

You can also start another universe with another map. For example : https://play.workadventure.minikube/_/anyuniverse/gparant.github.io/tcm-client/Demo/demo-v1.json

### Install workadventure in a specific Git branch

Branches are those in upstream repo (from https://github.com/thecodingmachine/workadventure)

```
helm install myrelease . --set image.tag=develop
```

### Install workadventure with a specific domain
```
helm install myrelease . --set domain=mydomain.com
```

It will then be available at https://play.mydomain.com/_/global/maps.mydomain.com/Floor0/floor0.json


## Customise

You can override any values defined [values.yaml](./values.yaml). Read Helm doc to know how.

## TODO

[X] TLS in order to make camera and mic working

[ ] Depend from Jitsi Helm to get full self-hosting

[ ] Simplify templates ?

[ ] CI/CD this Chart
