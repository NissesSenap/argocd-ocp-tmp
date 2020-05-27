# CLI

There is so many cli:s now a days so I have a hardtime remeberd them all so here is a few basic ones.

## Basic

### login

argocd login <endpoint>

### Create example app

If the application in the same cluster as argocd is, the dest-server is correct.
If you do bellow command from OCP it won't work due to root access

argocd app create guestbook --repo https://github.com/argoproj/argocd-example-apps.git --path guestbook --dest-server https://kubernetes.default.svc --dest-namespace argocd

### Get specific app status

argocd app get guestbook
