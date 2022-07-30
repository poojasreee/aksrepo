# aksrepo![arch](https://user-images.githubusercontent.com/107124664/181870403-756f12ae-4772-4128-ad84-1e661706e170.PNG)
Pre-requistes:
1. AKS cluster & container registry needs to be up running. created via azure piplelines using azure cli
https://dev.azure.com/poojasrikarapureddy/pooja.build/_apps/hub/ms.vss-build-web.ci-designer-hub?pipelineId=25&branch=azure-pipelines

2. Dockerfile created along with the index.html - used nginx image for application
3. Make sure AKS has pull access from ACR - as it is a private repository

command : az aks check-acr -g my-rg -n my-cluster --acr myregistry.azurecr.io -- for verifying the push access

created build & deploy in the same pipeline
![services](https://user-images.githubusercontent.com/107124664/181915832-06635bae-1870-4797-b29e-570b2d5b6c4d.PNG)

refer - azurepipelines.yml

generated manifests from kubenetes folder in this repo.
publish & download done for manifests and then deployed that image from ACR to AKS using deploy stage in pipeline.

once build succeded got the hello world output

![kubernetes](https://user-images.githubusercontent.com/107124664/181915630-82c425ae-f184-40fe-94a1-ff24e515ad79.PNG)

![pods](https://user-images.githubusercontent.com/107124664/181915846-e24c81b8-0145-4921-ba36-7e7f9fe7d4d2.PNG)

![podsoutput](https://user-images.githubusercontent.com/107124664/181916426-30a9b58c-8001-4de5-a61b-4a9329a7a9be.PNG)
