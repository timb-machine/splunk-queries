# splunk-queries

## Queries

* Which indexes are most heavily utilised:

```| eventcount summarize=false index="*" | stats sum(count) by index | sort sum(count) | reverse```

* What source types go into what indexes:

```index="*" | stats count by sourcetype, index```

* Get a summary of what a specific index looks like:

```index=<name of index> | fieldsummary```
