# lab10
#polecenia
docker network create lab10net
mkdir ~/lab10/web1_logs
mkdir ~/lab10/web2_logs
mkdir ~/lab10/web3_logs
docker run -d --name web1 --network lab10net -p 8081:80 -v C:\Users\Mariia\lab10:/usr/share/nginx/html:ro -v C:\Users\Mariia\lab10\web1_logs:/var/log/nginx nginx:latest
docker run -d --name web2 --network lab10net -p 8082:80 -v C:\Users\Mariia\lab10:/usr/share/nginx/html:ro -v C:\Users\Mariia\lab10\web2_logs:/var/log/nginx nginx:latest
docker run -d --name web3 --network lab10net -p 8083:80 -v C:\Users\Mariia\lab10:/usr/share/nginx/html:ro -v C:\Users\Mariia\lab10\web3_logs:/var/log/nginx nginx:latest
docker ps
docker logs web1
docker logs web2
docker logs web3
