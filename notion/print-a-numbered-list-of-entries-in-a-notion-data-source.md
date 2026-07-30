# Print a Numbered List of Entries in a Notion Data Source

Using the Notion CLI and `jq`, we can print the name of every entry in a Notion data source:

```
ntn api v1/data_sources/<data_source_id>/query \
  sorts:='[{"property":"Name","direction":"ascending"}]' \
  page_size:=100 | jq -r '[.results[].properties.Name.title[0].plain_text | select(. != null)] | to_entries | .[] | "\(.key + 1). \(.value)"'
```

What you’ll need to install:
- `ntn` (Notion’s CLI)
- `jq`  

What you’ll need to provide:
- Data source ID
- Page size (default: 100)

## Data Source vs. Database

Data sources are not the same as databases. From [Notion’s docs](https://developers.notion.com/reference/data-source):
> Data sources are the individual tables of data that live under a Notion database. Pages are the items (or children) in a data source.

## Printing Different Properties

Note that `.results[].properties.Name.title[0].plain_text` is the specific path Notion uses for database page titles. If you’re targeting a property other than `Name`, you’ll need to change this to the correct path for that property.

---

[Notion CLI | Notion Docs](https://developers.notion.com/cli/get-started/overview)

[Retrieve a data source | Notion Docs](https://developers.notion.com/reference/retrieve-a-data-source)

[jq](https://jqlang.org/)
