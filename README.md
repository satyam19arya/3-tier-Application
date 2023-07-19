## 🏠 Architecture
![architecture](https://github.com/satyam19arya/3-tier-Application/assets/77580311/1b6db6cc-e659-4b09-b565-85574f3b477b)

## Tech stack

- React (FRONTEND)
- Nodejs (BACKEND)
- MySQL (DATABASE)

## 🖥️ Installation of frontend

**Note**: You should have nodejs installed on your system

👉 let install dependency to run react application

```sh
cd client
npm install
```

**Note**: you have to change one file for backend API. you will find that `src/pages/config.js`

```sh
vim src/pages/config.js
```

```javascript
const API_BASE_URL = "https://api.yourdomain.xyz";
export default API_BASE_URL;
```
make sure you EDIT above file depends on your scenario

```sh
npm run build 
```

above command creat optimize build of the application in client folder. `build/` you will find all the files that you can serve through **Apache** or **Nginx**

##  🖥️ ️Installation of backend

**Note**: You should have nodejs installed on your system.

👉 let install dependency to run Nodejs  API

```sh
cd backend
npm install
```
Now we need to create .env file that holds all the configuration details of the backend. you should be in backend directory

```sh
vim .env
```
add below content 

```javascript
DB_HOST=localhost or URL_of_RDS
DB_USERNAME=user_name_of_MySQL
DB_PASSWORD=passwod_of_my_sql
PORT=3306
```
**Note** : please change above file depending on your setup. like you may use RDS(AWS) or Local mysql-server on your system. your mysql contain database with the name of `test` and it should has `books` table. You can you test.sql to create table 


```sh
mysql -h <<RDS_ENDPOINT OR localhost>> -u <<USER_NAME>> -p<<PASSWORD>>

CREATE DATABASE test;

mysql -h <<RDS_ENDPOINT OR localhost>> -u <<USER_NAME>> -p<<PASSWORD>> test < test.sql
```


please install pm2 if you want to run on cloud. you may need sudo privilages to installed it because we are going to installed globally.

```sh
npm install -g pm2
```

now you can run this application. make sure you are in backend directory


```sh
pm2 start index.js --name "backendAPI"
```

above command will start node server on port 80, you can modify the port number in `index.js` file
Now we are Ready to see the application😊
