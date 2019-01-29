---
page: page
---

### Use case: Backup

Start storage server
```
backup-host:~$ hs start --store_dir ~/store --port 9753 start &> store.log &
backup-host:~$
```

Create invitation
```
backup-host:~$ shashd invite --store_dir ~/store
9d739ff3-c218-4a52-a6c3-22fb669c74df
backup-host:~$
```

Register directory to backup on
```
desktop:~$ shash register --dir ~/work --url http://backup-host:9753/ --invitation 9d739ff3-c218-4a52-a6c3-22fb669c74df
desktop:~$
```


Every time you want to backup:
```
desktop:~$ shash backup --dir ~/work
desktop:~$
```

`--dir` option could be ommited, then it assumed to be current directory.

```
desktop:~/work$ shash backup
desktop:~/work$
```
