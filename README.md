# splunk-queries(https://www.splunk.com/)

![](https://img.shields.io/github/last-commit/timb-machine/spunk-queries?style=for-the-badge)

[Rolling 7 day view of updates from this repo](https://github.com/timb-machine/splunk-queries/compare/main@%7B7day%7D...main)

[Submissions?](https://github.com/timb-machine/splunk-queries/blob/main/doc/HACKING)

The following is my scribbled notes on some fun queries that yield results when you feed them into [Splunk]([https://codesearch.debian.net](https://www.splunk.com/)).

## Queries

* Which indexes are most heavily utilised:

```| eventcount summarize=false index="*" | stats sum(count) by index | sort sum(count) | reverse```

* What source types go into what indexes:

```index="*" | stats count by sourcetype, index```

* Get a summary of what a specific index looks like:

```index=<name of index> | fieldsummary```
