# WSL--Subsistema-Windows-para-Linux

Roda versões do Linux diretamento do Windows sem a necessidade de instalar uma maquina virtual, como o VirtualBox por exemplo.

wsl --install == comando para instalar o subsistema para Linux no windows.
wsl -l -o == lista as distribuições que podem ser instaladas. Para adicionar distribuições é recomendavel usar o Microsoft Store.

wsl --install -d nomeDaDistribuição == instala a distribuição para ser usada.

wsl -l == lista as versões Linux instaladas.

wsl -l -v == traz mais detalhes das distribuições instaladas.

wsl nomeDaDistribuição == inicializa a distribuição padrão.

DOCKER:

inicializar o serviço no Ubuntu == sudo service docker start.

docker images == lista as imagens disponiveis.

exemplo de comando para inicializar uma imagem docker Mysql, importante observar o uso do atributo -p indicando a que a porta 3306 do
docker também será a porta 3306 do Linux que esta rodando no WSL do Windows.

 docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=diogo -e MYSQL_PASSWORD=123 mysql:5.7
