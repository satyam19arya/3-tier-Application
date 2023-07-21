## Tech stack

- React (FRONTEND)
- Nodejs (BACKEND)
- MySQL (DATABASE)

## AWS Services used
- 🌐 Amazon Route 53
- 💻 Amazon EC2
- 🔐 Security Groups
- ⚖️ Amazon Autoscaling
- 🪪 Amazon Certificate Manager
- 🪣 Amazon Backup service
- 🗄️ Amazon RDS
- ☁️ Amazon VPC
- 🌍 Amazon CloudFront
- 🔐 Amazon WAF
- 👁️ Amazon CloudWatch

## 🖥️ Installation of frontend

**Note**: You should have nodejs installed on your system

👉 let install dependency to run react application

```sh
cd 3-tier-Application
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

```sh
npm install 
npm run build 
```

 `build/` you will find all the files that you can serve through **Apache** or **Nginx**
 To serve through apache
```sh
sudo cp -r build/* /var/www/html
```

##  🖥️ ️Installation of backend

**Note**: You should have nodejs installed on your system.

```sh
cd 3-tier-Application
cd backend
npm install
```
Now we need to create .env file that holds all the configuration details of the backend

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
**Note** : please change above file depending on your setup. You may use RDS(AWS) or Local mysql-server on your system. Your mysql contain database with the name of `test` and it should has `books` table. You can you test.sql to create table

```sh
npm install 
npm install dotenv
```

```sh
sudo apt install mysql-server -y
mysql -h <<RDS_ENDPOINT OR localhost>> -u <<USER_NAME>> -p<<PASSWORD>> test < test.sql
```

Please install pm2 if you want to run on cloud. you may need sudo privilages to installed it because we are going to installed globally.
```sh
npm install -g pm2
```

Now you can run this application. make sure you are in backend directory
```sh
pm2 start index.js --name "backendAPI"
```

above command will start node server on port 80, you can modify the port number in `index.js` file

Now we are Ready to see the application😊

## 🏠 Architecture
   Coming soon
