# MySQL 8 for docker

## 需求環境

1. docker
2. docker-compose

## 使用說明

### 修改啟動設定檔參數

```bash
cp docker-compose.yml.example docker-compose.yml
```

docker-compose.yml

```
MYSQL_ROOT_PASSWORD: root管理者密碼
MYSQL_DATABASE: 想創建的資料庫名稱
MYSQL_USER: 使用者帳號
MYSQL_PASSWORD: 使用者密碼
```

### 啟動`MySQL`

```bash
docker-compose up
```

### 背景啟動`MySQL`

```bash
docker-compose up -d
```

### 結束`MySQL`

```bash
docker-compose down
```

### 一些常用的操作指令

1. 查看目前有運行的`docker container`

```bash
docker ps
```

2. 連線到某個`docker container`

```bash
docker exec -it CONTAINER_ID bash
```

--- 以下指令請連線到`docker container`中執行 ---

3. 匯入資料庫

```bash
mysql -u 使用者帳號 -p 資料庫名稱 < filename.sql
```

4. 匯出資料庫

```bash
mysqldump -u 使用者帳號 -p 資料庫名稱 > filename.sql
```

5. 與資料庫連線

```bash
mysql -u 使用者帳號 -D 資料庫名稱 -p
```

--- 以下指令請連線到資料庫中執行 ---

6. 列出所有資料表

```
show tables from 資料庫名稱;
```

7. 列出資料表所有欄位名稱

```
show columns from 資料表名稱;
```

8. 檢索資料表所有內容

```
select * from 資料表名稱;
```

### 清空`MySQL`資料庫

將`mysqldata`資料夾刪除即可

```bash
rm -rf ./mysqldata
```
