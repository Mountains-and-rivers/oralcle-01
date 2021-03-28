# 数据库基本操作

启动容器

```
docker run -d --name dbalex -p 1521:1521 -e ORACLE_SID=dbalex -e ORACLE_PWD=oracle -e ORACLE_CHARACTERSET=AL32UTF8 -e SGA_SIZE=4G -e PGA_SIZE=2G -e DB_ROLE=primary -e ENABLE_ARCH=true -v /data/dbalex02:/opt/oracle/oradata registry.cn-hangzhou.aliyuncs.com/woqutech/oracle-database-11.2.0.4.0-ee:latest
```

登录容器

```
docker exec -ti dbalex bash
```

进入交互界面

```
sqlplus /nolog
```

基本操作

```
SQL> conn /as sysdba
Connected.

SQL>  show user;
USER is "SYS"

SQL>  create user root identified by 123456;

User created.

SQL>  grant connect,resource,dba to root;

Grant succeeded.

SQL>  alter user system identified by 123456;

User altered.

SQL> alter user sys identified by 123456;

User altered.

SQL>  alter profile default limit PASSWORD_LIFE_TIME UNLIMITED;
```



