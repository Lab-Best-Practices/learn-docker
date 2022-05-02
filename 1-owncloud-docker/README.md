# ownCloud with Docker

ref https://xuanthulab.net/cai-dat-owncloud-tao-dich-vu-luu-tru-dam-may-rieng-voi-docker.html

```
mkdir /owncloud/

chmod -R 777 /owncloud/


```

```
version: '3.1'

services:
  owncloud:
    image: owncloud # tạo container c-owncloud
    restart: always
    container_name: c-owncloud
    ports:
      - 9898:80
    volumes:
      - /owncloud/files:/var/www/html  # ánh xạ thư mục /home/ownclode-files vào container
    networks:
      - owncloud-network

  mysql:
    image: mysql
    restart: always
    container_name: c-mysql-owncloud
    environment:
      MYSQL_ROOT_PASSWORD: VietNam@2022         # password root, thay bằng pass tự đặt
    networks:
      - owncloud-network
    volumes:
      - /owncloud/db:/var/lib/mysql  # ánh xạ thư mục /home/ownclode-db vào container


networks:
  owncloud-network: # tạo network
    driver: bridge
```