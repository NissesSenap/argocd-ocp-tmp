# ARGOCD-tmp

This is temp repo that i will remove after a customer demo

## Install ArgoCD

This part should be create like an ansible role or soemthing but for now i will do it manually (I know writing manuall in a ArgoCD repo is wrong :D).

I currently want to get started with ArgoCD and I don't care to badly about long-term operations even if that is the goal of the repo. My current plan to manage access is to [follow](https://blog.openshift.com/openshift-authentication-integration-with-argocd/) and use dex.

### Setup

#### The OCP way

Open OLM UI and install the ArgoCD operator.

```shell
oc new-project argocd

oc create -f argocd/ArgoCD.yml

# If you wan't to give argocd service account cluster-admin
oc apply -f argocd/cluster-admin.yml

```

## App of Apps

My plan is to use helm overall in this repo, if someone else want to use kustomize or what ever templating language,
please feel free to do so. We will put it in another subfolder and it should be fine.
The more exampels the better.

You can use argocd to setup the sync but it's usefull to have when testing your helm chart.

I'm counting that you already have installed helm v3, if not see [here](https://helm.sh/docs/intro/install/)

### Setup app of apps

argocd app create apps \
    --dest-namespace argocd \
    --dest-server https://kubernetes.default.svc \
    --repo https://github.com/NissesSenap/argocd-ocp-tmp.git \
    --path app_of_apps/helm  
argocd app sync apps
