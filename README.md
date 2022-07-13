# WSL--Subsistema-Windows-para-Linux

Roda versões do Linux diretamento do Windows sem a necessidade de instalar uma maquina virtual, como o VirtualBox por exemplo.

wsl --install == comando para instalar o subsistema para Linux no windows.
wsl -l -o == lista as distribuições que podem ser instaladas. Para adicionar distribuições é recomendavel usar o Microsoft Store.

wsl --install -d nomeDaDistribuição == instala a distribuição para ser usada.

wsl -l == lista as versões Linux instaladas.

wsl -l -v == traz mais detalhes das distribuições instaladas.

wsl nomeDaDistribuição == inicializa a distribuição padrão.

DOCKER:

inicializar o serviço no Ubuntu == sudo service docker start
docker images == lista as imagens disponiveis.
