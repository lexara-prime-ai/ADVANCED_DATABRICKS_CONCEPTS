### Advanced Databricks Concepts

## Connecting to a remote PostgreSQL instance

```python
# Define required fields
driver = "org.postgresql.Driver"
url = "jdbc:postgresql://<database_url>/<database_name>"
table = "<schema_name>.<table_name>"
user = "<username>/<USER_ID>"
password = "<password>"

# Provide a pre-defined query
query = "(SELECT * FROM <table_name>) as results"

df = spark.read.format("jdbc")
  .option("driver", driver)
  .option("url", url)
  .option("dbtable", query)
  .option("user", user)
  .option("password", password)
  .load()

# OUTPUT -> The following output is a schema example
# id:integer
# organizationid:string
# name:string
# website:string
# country:string
# description:string
# founded:string
# industry:string
# numberofemployees:integer
```



