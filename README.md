# create-and-vary-a-licence-wiremock
This repo hosts the infrastructure code for hosting the create and vary a licence version of the [hmpps-community-api-wiremock](https://github.com/ministryofjustice/hmpps-community-api-wiremock) service. 

This is a service that is hosted in dev and stubs various probation endpoints, using information from prison systems to produce realistic responses.

This service is hosted in the `create-and-vary-a-licence-api-dev` namespace and should be accessible to other namespaces via https://cvl-probation-mock.hmpps.service.justice.gov.uk/

# Deploy new versions

To deploy a new version of this service delete the pod or scale the pods down to 0 and back up to 1. This will trigger pulling and deploying the latest version of the docker image. 

e.g:
```
kubectl -n create-and-vary-a-licence-api-dev \
      delete pod create-and-vary-a-licence-wiremock-hmpps-community-api-<pod version here>
```
