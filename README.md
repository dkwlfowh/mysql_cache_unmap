# mysql_cache_unmap



##### MYSQL의 경우 Data / index를 Innodb_buffer_pool(Memory)영역에 올려 사용하기띠문에 OS/Buffer cache 공간을 사용하지 않아도된다.
##### 하여 MySQL에서 사용하는 OS Buffer/Cache 공간을 unmap 시켜 Memory 영역을 관리하는 용도의 실행파일


### 0.GIT CLONE
```
[root@master ~]# git clone https://github.com/dkwlfowh/mysql_cache_unmap.git
```

### 1.GCC
```
[root@master ~]# cd mysql_cache_unmap/lee/mysql_cache_unmap/lib/
[root@master ~]# gcc -o unmap_cache unmap_cache.c 
```

### 2.EXECUTE
##### ./mysql_cache_unmap [bindary_log_dir] [relay_log_dir]
```
[root@master ~]# cd mysql_cache_unmap/lee/mysql_cache_unmap
[root@master mysql_cache_unmap]# ./mysql_cache_unmap /data/data /data/data
Bindary Log :  /data/data
Relay Log :  /data/data
-----------------------------------------------------------------------
Fri Nov 11 09:44:05 KST 2022 cache unmap.. start
-----------------------------------------------------------------------
Mem:        7732372     3687736      182816        5720     3861820     3704344
-----------------------------------------------------------------------
unmap processing.. /data/data/mysql.000001.. ok
unmap processing.. /data/data/mysql.000002.. ok
unmap processing.. /data/data/mysql.000003.. ok
unmap processing.. /data/data/mysql.000001.. ok
unmap processing.. /data/data/mysql.000002.. ok
unmap processing.. /data/data/mysql.000003.. ok
-----------------------------------------------------------------------
Mem:        7732372     3687584     1428528        5720     2616260     3704656
```

### 원작자
https://gywn.net/tag/unmap/
