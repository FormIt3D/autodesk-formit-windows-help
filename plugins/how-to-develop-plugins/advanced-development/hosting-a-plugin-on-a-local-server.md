# Hospedar um plug-in em um servidor local

Antes de visualizar um plug-in clonado no FormIt, é preciso hospedá-lo em um servidor local.

### **Visualizar o terminal no IDE**

Você tem a opção de iniciar o servidor dentro do Visual Studio Code, em vez de em uma janela de terminal separada. \*\*\*\* Antes de abrir um terminal, verifique se a pasta correta está aberta no Visual Studio Code.

Visualizar > Terminal (ou atalho Ctrl + \`)

![](<../../../.gitbook/assets/image (11).png>)

### Configurar um servidor HTTP

Um servidor HTTP que funciona bem é o [http-server](https://www.npmjs.com/package/http-server) do npm.

Primeiro, você precisará fazer o download e instalar o [NodeJS](https://nodejs.org/pt-br/), se ele ainda não estiver instalado.

Se você encontrar erros nas etapas a seguir, tente reiniciar o computador para concluir a instalação do NodeJS.

No prompt de comando, insira o seguinte para instalar o _http-server_ do npm globalmente (uma configuração única).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Iniciar o servidor local

Quando a configuração estiver concluída, execute o seguinte comando no terminal para iniciar o http-server do npm:

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Dica 1: No caso de problemas com a execução do http-server (instalado globalmente ou localmente), pode ser útil executá-lo diretamente via npx:

* `npx http-server`

Dica 2: Para usuários do Windows 10/11, se ocorrer um erro ao executar um script no novo computador, isso poderá ser devido às configurações estarem desativadas. Para corrigir esse problema:

* Inicie o script do PowerShell como administrador
* Configure: `Set-ExecutionPolicy RemoteSigned`

### Desenvolver para o FormIt para Web

Para desenvolver para o FormIt para Web, basta executar o seguinte comando:

* `http-server --cors`

![](<../../../.gitbook/assets/image (10).png>)

### Verificar o servidor

É possível verificar o servidor navegando até o seguinte endereço no navegador da Web:

* http://localhost:8080

Você deve ver os arquivos da pasta de projeto na janela do navegador.

\*\*Se você usar um servidor da Web diferente de npm, o endereço/porta padrão poderá ser diferente.

![](<../../../.gitbook/assets/image (41).png>)
