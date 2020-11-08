EXERCISE 3
==========

docker pull nginx:1.19.3
docker run -d -p 8080:80 --name nginx nginx:1.19.3

docker exec -it nginx /bin/bash
cd /usr/share/nginx/html
cat > index.html

docker volume create static_content
docker run -d -p 8080:80 nginx:1.19.3 /bin/bash --mount source=static_content,target=/usr/share/nginx/html/