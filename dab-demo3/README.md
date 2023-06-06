# Steps Demo3

Init configuration file

```bash
dab init --database-type mssql --connection-string "@env('DATABASE_CONNECTION_STRING')" --host-mode "Development"
```

Add Product entity

```bash
dab add Product --source SalesLT.Product --permissions "anonymous:*" --rest product
```

Add ProductCategory entity

```bash
dab add ProductCategory --source SalesLT.ProductCategory --permissions "anonymous:*" --rest productcategory
```

Add One-to-many relationship between ProductCategory and Product

```bash
dab update ProductCategory --relationship Products --target.entity Product --cardinality many
```

Add Many-to-one relationship between Product and ProductCategory

```bash
dab update Product --relationship ProductCategories --target.entity ProductCategory --cardinality one
```

Start locally

```bash
dab start
```
