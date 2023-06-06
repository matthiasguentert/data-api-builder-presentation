# Steps Demo1

Init configuration file

```bash
dab init --database-type mssql --connection-string "@env('DATABASE_CONNECTION_STRING')" --host-mode "Development"
```

Add entity

```bash
dab add Product --source SalesLT.Product --permissions "anonymous:*" --rest product
```

Add view

```bash
dab add vProductAndDescription --source.type view --source "SalesLT.vProductAndDescription" --permissions "anonymous:*" --rest productanddescription --source.key-fields ProductID
```

Start locally

```bash
dab start
```
