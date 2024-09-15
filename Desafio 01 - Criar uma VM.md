# Desafio 01

## Criação de uma Máquina Virtual/VM
Passo a passo de como criar uma maquina virtual no ambiente Azure.

### 01 - Acesse o site https://portal.azure.com/#home e entre com seu login e senha.


### 02 - Na página inicial, encontre a opção "Máquinas Virtuais".
<img src="/img/1-TELA INICIAL.png">


### 03 - Na página de Máquinas Virtuais, serão dadas 3 opções de criação:
<img src="/img/2-TELA INICIAL MAQUINA VIRTUAL.png">

Máquina Virtual Azure - Neste modo, você pode definir todas as configurações da sua máquina virtual, desde o sistema, armazenamento, rede até ferramentas de monitoramento. Garante maior flexibilidade para criar máquinas com configurações específicas.

Máquina Virtual Azure com Configuração Predefinida - Neste modo, você pode escolher entre modelos/imagens de máquinas virtuais pré-definidas pela Azure, que já vêm com certas configurações e permitem alguns ajustes. Garante maior rapidez na criação de uma máquina virtual para usos específicos.

Mais VMs e Soluções Relacionadas (Outras Soluções de VM no Azure) - Neste modo, é possível escolher modelos de configuração específicos, como, por exemplo, a contratação de máquinas por 1 ano, que oferece um grande desconto. Tabela de Modelos.

### 04 - Após selecionar o modelo, defina as configurações possíveis para o mesmo. Seguindo o modelo Máquina Virtual Azure, onde se tem grande flexibilidade, defina as principais informações como: Nome da VM, Sistema Operacional, Região onde será criada, Zona de Disponibilidade, RAM, armazenamento, entre outros. Uma última informação importante é o login e senha que serão usados para conectar na VM (também é possível utilizar conexão por SSH).
<img src="/img/3-TELA CONFIGURAÇÃO VM.png">
<img src="/img/4-TELA FINAL VM.png">

### 05 - Após a criação, vá na parte de recursos ou máquinas virtuais, onde será possível visualizar a máquina criada, acompanhar todas as informações da mesma.
<img src="/img/5-TELA RECURSOS.png">

### 06 - Para conectar na VM criada, abra um Bash/PowerShell e digite o comando `ssh nome_usuario@ip_publico_VM` . A depender do tipo de conexão escolhido na criação da VM, será solicitada uma senha ou a confirmação da chave SSH para que a conexão seja estabelecida. Após a conexão, você estará em um terminal/CLI, onde poderá inserir comandos como: pwd (mostra o caminho do diretório atual), ls (lista os arquivos no diretório atual), cd caminho (entra no caminho especificado). Caso tenha escolhido a imagem do Windows Server, você terá uma interface semelhante à do próprio Windows na sua VM.
<img src="/img/6-CONECTANDO NA VM.png">

**OBS**: Para a conexão atraves de SSH, ao final da criação da VM, o Azure pede que você baixe um arquivo que contem a sua chave privada SSH, que será usada para autenticar a conexão com a VM, mova esse arquivo para um diretorio( geralmente é usado o direito C:\users\nome_usuario\), toda essa configuração é feita na pasta .ssh que é criada no direito do usuario, você pode cria-la manualmente, ou, ao tentar fazer a conexão com a VM a primeira vez, usando esse comando `ssh nome_usuario@ip_publico_VM`, ele irá avisar que você nunca se conextou aquele servidor e pedira uma confirmação, ao aceitar, ele irá criar a pasta .ssh automaticamente e irá adicionar um arquivo chamado `known_hosts` que armazena quais servidores você já se conectou.Bom, apos configurar essa parte da pasta,colocando o arquivo da chave privada nela, abra um terminal nela e digite o seguinte código `ssh -i arquivi_chavePrivada.pem nome_usuario@ip_publico_VM`, com isso, será estabelecida a conexão com a VM.
<img src="/img/7-CONF SSH.png">