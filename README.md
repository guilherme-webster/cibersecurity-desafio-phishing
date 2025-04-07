# Phishing para captura de senhas do Facebook

### Ferramentas

- Kali Linux
- setoolkit

### Configurando o Phishing no Kali Linux

- Acesso root: ``` sudo su ```
- Iniciando o setoolkit: ``` setoolkit ```
- Tipo de ataque: ``` Social-Engineering Attacks ```
- Vetor de ataque: ``` Web Site Attack Vectors ```
- Método de ataque: ```Credential Harvester Attack Method ```
- Método de ataque: ``` Site Cloner ```
- Obtendo o endereço da máquina: ``` ifconfig ```
- URL para clone: http://www.facebook.com

### Resutado de uma página do facebook sem defesa

![print do terminal mostrando a senha e usuario](./passwd.png "resultado sem defesa")

### Resultado de uma página do facebook com defesa

![print do terminal que nao revela nada](./def_face.png "resultado com defesa")

- Isto ocorre porque sites como o facebook detectam o phishing primitivo que estamos tentando realizar

### Como burlar esta defesa inicial

Usaremos um Custom Import de modo a clonar o código fonte da página original.


### Primeira etapa

Entramos na página original do facebook e baixamos ela no nosso computador, aproveitamos para copiar o source code da página e guardar o id do botão de login

### Segunda etapa

Colamos o código fonte no html baixado e procuramos o id do botão no código. A linha de cima será o script que irá executar a ação do botão, nós removemos ela. Aproveitamos e trocamos o nome do html para index.html.

![printa da linha a ser removida](./remove_from_script.png "linha a ser removida")

### Terceira etapa

Copiamos o path para a página do facebook e index.html

![print da folder com a pagina destacando o path](./path.png "path")

### Quarta etapa

Agora, seguimos o mesmo passo a passo original, mas optamos por Custom Import, colamos o caminho copiado, e selecionamos para copiar toda a folder.

![print do comando](./actual_command.png "comando para o phishing com custom import")

### Quinta etapa

Agora, efetivamente, "pescamos" nosso alvo!

![print da pagina falsa do facebook](./fake_face.png "pagina do face falsa")

E quando o usuario tenta logar...

![print do terminal do hacker com o login do alvo vazado](./login.png "login vazado")