# ArchiSteamFarm

[ASF](https://github.com/JustArchiNET/ArchiSteamFarm) is a C# application with primary purpose of farming Steam cards from multiple accounts simultaneously.

## Introduction

This chart bootstraps an ASF instance for remote usage.

This chart requires persistence to be set up.

## Installing the chart

To install the chart:

```sh
helm repo add g0dscookie https://charts.copr.icu
helm install g0dscookie/archisteamfarm
```

## Configuration

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| image.repository | OCI image to use | ghcr.io/justarchinet/archisteamfarm |
| image.pullPolicy | pull policy | IfNotPresent |
| image.tag | image tag to use | Chart.AppVersion |
| initImage.repository | OCI image for init container | busybox |
| initImage.pullPolicy | pull policy | IfNotPresent |
| initImage.tag | image tag to use | stable |
| imagePullSecrets | pull secrets to pull the images | [] |
| nameOverride | override chart name | "" |
| fullnameOverride | override full chart name | "" |
| initialPassword | ASF IPC initial password | "" |
| steamId | Steam ID used by ASF to do steam requests | "0" |
| hostname | hostname where ASF should be available | asf.example.org |
| podAnnotations | pod annotations | {} |
| podSecurityContext | pod security context | {} |
| securityContext | container security context | {} |
| ingress.enabled | enable ingress | true |
| ingress.className | ingress class name | "" |
| ingress.annotations | ingress annotations | {} |
| certmanager.enabled | enable cert-manager | true |
| certmanager.issuerType | cert-manager isser type (Issuer, ClusterIssuer) | ClusterIssuer |
| certmanager.issuerName | name of cert-manager issuer to use | letsencrypt |
| certmanager.apiVersion | api version of cert-manager to use | cert-manager.io/v1 |
| persistence.size | size of PVC | 1Gi
| persistence.storageClass | storage class for PVC | "" |
| persistence.accessMode | access mode for PVC | ReadWriteOnce |
| persistence.claimNameOverride | use custom PVC | "" |
| persistence.annotations | annotations for PVC | {} |
| resources | pod resource limits | {} |
| nodeSelector | pod node selector rules | {} |
| tolerations | pod toleration rules | [] |
| affinity | pod affinity rules | {} |
