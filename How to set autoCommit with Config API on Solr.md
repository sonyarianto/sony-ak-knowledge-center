Enabling auto soft-commits with maxTime 3 secs using the Config API

POSTing request to Config API: http://localhost:8983/solr/techproducts/config
```
{"set-property":{"updateHandler.autoSoftCommit.maxTime":"3000"}}
```
