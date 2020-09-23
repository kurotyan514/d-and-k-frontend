### 75. bookmarking volumes

```
docker run -it -v /app/node_modules -v $(pwd):/app -p 3000:3000 bf35886237f2
```

第一個 `-v` 沒有 `:` 代表不要把 container裡的某個node_modules reference到local
目錄下的node_module(因為已經刪掉了)
第二個 `-v` 的 `$(pwd)` 代表現在的目錄，所以 `$(pwd):/app`的意思是
把 container 裡的某個path下的檔案 reference 到現在在local的目錄下

### 81. Excuting test
```
docker run -it IMAGE yarn test
```

### 82. Live Updating Tests
重複利用已經起起來的 docker-compose container 跑 test

```
docker-compose up
# open another terminal

# find container name
docker-compose ps 
docker exec -it CONTAINER yarn test
```
