# docker-destop
# 2 สร้างโปรเจค
mkdir student-docker

cd student-docker






# สร้างไฟล์ student-docker

```yaml
services:
  mysql:
    image: mysql:8.0
    container_name: student_mysql
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: student_db
    ports:
      - "3306:3306"
    volumes:
      - student_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin:latest
    container_name: student_phpmyadmin
    restart: unless-stopped
    environment:
      PMA_HOST: mysql
      PMA_PORT: 3306
    ports:
      - "8080:80"
    depends_on:
      - mysql

volumes:
  student_data:
```

# 3 รัน
docker compose up -d

# 4 phpMyAdmin
http://localhost:8080




