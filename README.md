# Comandos-Docker

- docker ps ---> lista os container
- docker ps -a ---> lista também os containers que já foram executado e já morreram
- docker run ubuntu ---> baixa uma imagem do ubuntu caso não esteja baixada
- docker run -it --rm ubuntu:latest bash ---> Inicia o processo do container com comando bash e ao fechar o container automaticamente o container é removido
- docker run -d -p 8080:80 nginx ---> libera a porta 8080 para acessar o nginx e com '-d' não fica preso no terminal
- docker run --name nginx -d -p 8080:80 nginx ---> libera a porta 8080 para acessar o nginx e com '--name' defini o nome do meu container
- docker run --name nginx -d -p 8080:80 -v /home/html:/usr/share/nginx/html nginx ---> libera a porta 8080 para acessar o nginx e com '-v' manda o 'html' para o volume criado
- docker run --name nginx -d -p 8080:80 --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html nginx ---> libera a porta 8080 para acessar o nginx e com '--mount type=bind,source=' manda o 'html' para o volume criado. (Forma mais nova usada)
- docker volume create meuvolume ---> cria um volume com o nome meuvolume
- docker run --name nginx -d -p 8080:80 --mount type=volume,source=meuvolume,target=/app nginx ---> libera a porta 8080 para acessar o nginx e passa o nome do volume que já fora criado.
- docker rm nome_container ---> remover o container
- docker rm nome_container -f ---> remover o container forçando, mesmo sem dar stop para parar
- docker exec -it nginx bash ---> executa o bash já no container criado
- docker volume prune ---> mata tudo que não está sendo usado nos volumes
