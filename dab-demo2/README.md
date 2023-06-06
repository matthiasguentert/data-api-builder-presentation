# Steps Demo2

Init configuration

```bash
dab init --database-type mssql --connection-string "@env('DATABASE_CONNECTION_STRING')" --host-mode "Development" --auth.provider "AzureAD" --auth.audience "<app-id>" --auth.issuer "https://login.microsoftonline.com/<tenant-id>/v2.0"
```

Add an entity

```bash
dab add Product --source SalesLT.Product --permissions "contributor:read,create" --rest product
manually add "admin:*"
```

Fetch token

```bash
az login --scope api://<app-id>/endpoint.access
az account get-access-token --scope api://<app-id>/endpoint.access --query accessToken --output tsv
```
