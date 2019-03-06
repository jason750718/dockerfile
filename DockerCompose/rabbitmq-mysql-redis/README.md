將 MySQL 初始資料放在 mysql\sql-scripts, Container起來後會掛載到 /docker-entrypoint-initdb.d 底下執行
下一行指令是為了在 Windows 以及 Mac 上啟動 MariaDB
mysqld --innodb-flush-method=littlesync --innodb-use-native-aio=OFF --log_bin=ON

run docker-compose up -d

