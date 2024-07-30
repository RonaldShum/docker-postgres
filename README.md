# docker-postgres

Use the following command to create a docker container for postgres db

```docker run --name postgres-db -e POSTGRES_PASSWORD=password1234 -p 5432:5432 -d postgres```
![image](https://github.com/user-attachments/assets/092fe08f-72f6-42e1-ac1e-904ac7c0dc93)

Use docker ps to check the container is running

```docker ps```
![image](https://github.com/user-attachments/assets/62161ff6-3231-4b10-a5ea-9113796e32f5)

Your postgres db is now running in the container, you can use localhost:5432 to access your postgres db.
Username: postgres
Password: password1234
host: localhost
port: 5432
![image](https://github.com/user-attachments/assets/ea71cb68-8d8e-466f-9816-e4dd2d5ab38d)

Now run the pgadmin 4 in docker container

```docker run --name pgadmin-container -p 18010:80 -e PGADMIN_DEFAULT_EMAIL=user@domain.com -e PGADMIN_DEFAULT_PASSWORD=password1234 -d dpage/pgadmin4```
![image](https://github.com/user-attachments/assets/3a0a22e5-80c1-48b4-b8c2-4d52fb46ebd7)

Go to localhost:18010 for the pgadmin4 and login with the account
username: user@domain.com
password:password1234
![image](https://github.com/user-attachments/assets/145da10f-5ecb-491a-8af9-7eff45679eaa)

Before you add the new server, get the ip address for your pgadmin to connect to postgres.

```docker inspect postgres-db```

Look for the ip address, in my case, it is 172.17.0.2
![image](https://github.com/user-attachments/assets/748269ce-a771-4d44-908f-fa07d8bd982b)

Use the ip you get as host to connect to your postgres db and do your thing (i.e. create new account, db table etc)
host name/address: 172.17.0.2
username: postgres
password: password1234

![image](https://github.com/user-attachments/assets/d5bbd8a5-2f5b-4560-bf03-0ccfbf0d62a6)

Now you can go back to your intellji and access the db with the new account. 
However, remember when accessing your db outside of the pgadmin, you would use localhost:5432 !

