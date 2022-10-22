# WSL--Subsistema-Windows-para-Linux

Roda versões do Linux diretamento do Windows sem a necessidade de instalar uma maquina virtual, como o VirtualBox por exemplo.

<strong>wsl --install</strong> == comando para instalar o subsistema para Linux no windows.<br/>
<Strong>wsl -l -o</strong> == lista as distribuições que podem ser instaladas. Para adicionar distribuições é recomendavel usar o Microsoft Store.

<strong>wsl --install -d nomeDaDistribuição</strong> == instala a distribuição para ser usada.

<strong>wsl -l</strong> == lista as versões Linux instaladas.

<strong>wsl -l -v</strong> == traz mais detalhes das distribuições instaladas.

<strong>wsl nomeDaDistribuição</strong> == inicializa a distribuição padrão.

<h2>DOCKER</h2>

inicializar o serviço no Ubuntu == sudo service docker start.

docker images == lista as imagens disponiveis.

exemplo de comando para inicializar uma imagem docker Mysql, importante observar o uso do atributo -p indicando a que a porta 3306 do
docker também será a porta 3306 do Linux que esta rodando no WSL do Windows.

 docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=diogo -e MYSQL_PASSWORD=123 mysql:5.7 == este comando cria um novo container e aporta 3306 do host foi redirecionada para a porta 3306 do container, então quando é acessado http://localhost:3306 é acessado o container na porta 3306. Essa é uma regra de iptables.
 
 iptables -t nat -L -n é possível ver o redirecionamento.
 
 <p>
 <strong>docker exec -it meu_container /bin/bash </strong><br>
 Esse comando irá executar um o bash que é nosso console no linux.
 A flag -i permite mapear a entrada do teclado para o bashs e -t reserva o terminal.
 
 </p>
 
 <h2>Comandos Linux Úteis</h2>
 <p><strong>cat /etc/osrelease</strong> === verifica versão do Linux Ubuntu</p>
