# Setup of ArgoCD

ArgoCD.yml will create a argocd instance for you and a service account.

My ArgoCD deployment is supposed to handle all infra parts so i created cluster-admin.yml

In short i give cluster-admin access to ArgoCD.

I my mind a normal user should never login directly to the cluster to perfrom administration tasks, instead
ArgoCD should be doing everything. Thanks to this we will be able to track everything that happens.

Of course there should be a "break" glass user that is cluster-admin that can login and fix stuff manually if needed.
