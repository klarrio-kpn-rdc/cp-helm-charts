# cp-helm-charts-fork
# What is it?
`cp-helm-charts-fork` is our own fork of the cp-helm-charts repo. Currently datahub uses its own schema registry which
is contained in these helm charts. This fork was necessary to add the required TLS configuration to connect with the
Strimzi cluster

# Details
In order to add these helm charts to a helm chart repository do following steps.
First package the helm charts via

`helm package ../cp-helm-charts`

Then move the created tarball to the docs folder:

`mv cp-helm-charts-0.6.1.tgz docs/cp-helm-charts-0.6.1.tgz`

Afterwards remake the index file used by the github pages:

`helm repo index docs/ --url https://klarrio-kpn-rdc.github.io/cp-helm-charts/`

Push everything to git:

```
git add --all
git commit -m "<message>"
git push origin gh-pages
```

And finally, add the repo to your local repositories:

`helm repo add cp-helm-charts https://klarrio-kpn-rdc.github.io/cp-helm-charts/`


