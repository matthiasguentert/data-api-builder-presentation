# Hosting with Azure Container Apps

Create resource group

```bash
az group create --name rg-demo --location "westeurope"
```

Create Storage Account

```bash
az storage account create --resource-group rg-demo --name stdabdemo8912 --location "westeurope" --sku Standard_LRS
```

Create Storage File Share & Upload dab-config.json

```bash
az storage share create --resource-group rg-demo --storage-account stdabdemo8912 --name dab-config 
```

Create Container Instance

```bash
az container create --resource-group rg-demo --file containerinstance.yaml
```
