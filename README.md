# WSL--Subsistema-Windows-para-Linux

Roda versões do Linux diretamento do Windows sem a necessidade de instalar uma maquina virtual, como o VirtualBox por exemplo.

<h2>Comandos</h2>
<strong>wsl --install</strong> == comando para instalar o subsistema para Linux no windows.<br/>
<Strong>wsl -l -o</strong> == lista as distribuições que podem ser instaladas. Para adicionar distribuições é recomendavel usar o Microsoft Store.

<strong>wsl --install -d nomeDaDistribuição</strong> == instala a distribuição para ser usada.

<strong>wsl -l</strong> == lista as versões Linux instaladas.

<strong>wsl -l -v</strong> == traz mais detalhes das distribuições instaladas.

<strong>wsl nomeDaDistribuição</strong> == inicializa a distribuição padrão.

<h2>Resetando a senha de usuário no WSL</h2>

<strong>wsl -l -v</strong> === lista as distruições linux instaladas no wsl do Windows.<br>
<strong>wsl -d NOMEDADISTRIBUICAO --user root</strong><br>
<strong>passwd NOMEDOUSUARIO</strong> == já dentro do Linux executar este último comando e redefinir a senha.

<h2>DOCKER</h2>

inicializar o serviço no Ubuntu == <strong>service docker start</strong>.

<strong>docker images</strong> == lista as imagens disponiveis.

<strong>docker ps</strong> == lista os containers em atividade.<br/>
<strong>docker ps -a </strong> == lista todos os containers, incluindo os que estiverem parados.<br/>
<strong>docker system prune -a</strong> == limpa containeres nao utilizados.<br/>
<strong>docker volumes prune</strong> == remove volumes nao utilizados.<br/>
<strong>docker rmi <image_id></strong> == serve para excluir uma imagem do disco local.<br/>

exemplo de comando para inicializar uma imagem docker Mysql, importante observar o uso do atributo -p indicando a que a porta 3306 do
docker também será a porta 3306 do Linux que esta rodando no WSL do Windows.

 docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=diogo -e MYSQL_PASSWORD=123 mysql:5.7 == este comando cria um novo container e aporta 3306 do host foi redirecionada para a porta 3306 do container, então quando é acessado http://localhost:3306 é acessado o container na porta 3306. Essa é uma regra de iptables.
 <p>Exemplo de container docker com postgres ===  <strong>docker run -v postgres-dados:/var/lib/postgresql/data -p 5432:5432 -e POSTGRES_PASSWORD=123 postgres</strong>. Pode-se adicionar a opção -d para rodar em segundo <em>background</em></p>
 
 iptables -t nat -L -n é possível ver o redirecionamento.
 
 <h3>Volumes docker</h3>
 <strong>docker volume create NOMEVOLUME</strong> === cria um novo volume docker.<br>
 <strong>docker volume ls</strong> === lista os volumes docker disponíveis.
 
 <p>
 <strong>docker exec -it meu_container /bin/bash </strong><br>
 Esse comando irá executar um o bash que é nosso console no linux.
 A flag -i permite mapear a entrada do teclado para o bashs e -t reserva o terminal.
 
 <h2>DOCKER-COMPOSE</h2>
 <p>Configurado atraves de um arquivo <strong>YAML</strong> tem a capacidade de rodar varios containers, sem a necessidade de subir cada container manualmente.</p>
  <p>YAML (uma sigla que significa YAML Ain’t Markup Language) não é propriamente uma linguagem de programação mas sim uma sintaxe para a criação de ficheiros de configuração. A estrutura do YAML é determinada pela sua indentação, sendo a indentação definida pelo numero de espaços no inicio da cada linha e podem ser zero, dois ou múltiplos de dois. A estrutura de cada bloco é constituída por níveis, sendo que o nível anterior é considerado parent e o inferior children. O caracter - indica o inicio de uma listagem de variaveis ou atributos que se encontram ao mesmo nível, e que deve ser considerado na contagem de espaços na indentação. Em YAML os comentários são indicados pelo caracter #. Se o comentário estiver entre dois blocos de código deve ser escrito sem espaços à esquerda, se for escrito após uma linha de código deve sempre ser precedido de um espaço ou de uma ou mais tabulações para que os comentários fiquem alinhados.</p>
  
<strong>docker-compose -f <nomdeDoArquivo.yml> up</strong> === subindo os containers com um único comando.
 
 </p>
 <h2>Erro ao inicializar Docker no WSL</h2>
 <p>failed to start daemon: Error initializing network controller: error obtaining controller instance: unable to add return rule in DOCKER-ISOLATION-STAGE-1 chain:  (iptables failed: iptables --wait -A DOCKER-ISOLATION-STAGE-1 -j RETURN: iptables v1.8.7 (nf_tables):  RULE_APPEND failed (No such file or directory): rule in chain DOCKER-ISOLATION-STAGE-1
 (exit status 4))</p>
 <strong>Solução</strong>
 <p>sudo update-alternatives --set iptables /usr/sbin/iptables-legacy<br>
sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
</p>
 
 <h2>Comandos Linux Úteis</h2>
 <p><strong>cat /etc/os-release</strong> === verifica versão do Linux Ubuntu</p>
