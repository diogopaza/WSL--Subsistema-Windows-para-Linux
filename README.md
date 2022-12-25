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

 
 <h2>Comandos Linux Úteis</h2>
 <p><strong>cat /etc/os-release</strong> === verifica versão do Linux Ubuntu</p>
