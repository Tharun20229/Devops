from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Edge()
driver.get("https://www.google.com")

time.sleep(5)   # wait for 5 seconds

e = driver.find_element(By.NAME, "q")

print(e.tag_name, e.get_attribute("type"))

driver.quit()


from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Edge()
driver.get("https://www.google.com")

search = driver.find_element(By.NAME, "q")
btn = driver.find_element(By.NAME, "btnK")

print(search.is_displayed(), btn.is_enabled())

search.send_keys("Selenium")

driver.quit()

from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Edge()
driver.get("https://www.facebook.com")

driver.find_element(By.ID, "email")
driver.find_element(By.ID, "pass")
driver.find_element(By.NAME, "login")

print("Login page elements found")

driver.quit()




2
cd C:\Users\kallu\hello-docker
notepad index.html
notepad Dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
dir
ren Dockerfile.txt Dockerfile
docker build -t hello-app .
docker run -d -p 8080:80 hello-app
http://localhost:8080
3
mkdir alpine-nano
cd alpine-nano
Create Dockerfile 
FROM alpine:latest
RUN apk add --no-cache nano
CMD ["sh"]
Build image 
docker build -t alpine-nano .
Run container 
docker run -it --name nano-test alpine-nano
Verify Nano
Inside the container, type:
Nano  # If Nano opens, it is installed successfully.
4
mkdir mysql-docker
cd mysql-docker
Create Dockerfile 
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=root123
ENV MYSQL_DATABASE=testdb
EXPOSE 3306
Build Docker Image 
docker build -t mysql-app .
Run MySQL Container 
docker run -d -p 3307:3306 --name mysql-container mysql-app
Access MySQL inside Container 
docker exec -it mysql-container mysql -u root -p
Enter password: root123
Execute Simple Query 
SHOW DATABASES;
Create Table and Insert Data
USE testdb;

CREATE TABLE student (
    id INT,
    name VARCHAR(50)
);
INSERT INTO student VALUES (1, 'Tharun');
SELECT * FROM student;

5
Create the project folder 
mkdir mysql-phpmyadmin
cd mysql-phpmyadmin
Create the Dockerfile 
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=root123
ENV MYSQL_DATABASE=sampledb
EXPOSE 3306
Build the MySQL image 
docker build -t my-mysql-image .
Run the MySQL container 
docker run -d --name mysql-container1 -p 3307:3306 my-mysql-image
Run phpMyAdmin container 
docker run -d --name phpmyadmin-container -e PMA_HOST=host.docker.internal -e PMA_PORT=3307 -p 8081:80 phpmyadmin/phpmyadmin
Open phpMyAdmin 
http://localhost:8081
Login 
Username: root
Password: root123




