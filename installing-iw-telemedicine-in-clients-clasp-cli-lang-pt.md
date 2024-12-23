# Etapa 2 - Instalação IW-Telemedicine no Google Workspace do Cliente

>somente deve ser executada após o cumprimento de todos os passos da etapa1 (pré-instalação)  
sugerimos usar WLS2 com Ubuntu 20.04 e o terminal do Linux para executar os comandos abaixo.

1. **instalar os seguintes apps: git, nvm (node versions manager), NodeJS (latest 20), clasp (latest 2.4.2)**  
Todos esses progranas podem ser instalados em qualquer Sistema Operacional (Windows, Linux, MacOS).  
É recomendado usar Linux porque os apps de linha de comando como esses normalmente foram escritos pensando em Linux.  
Windows 10/11 oferece recurso de uso do Linux e Windows ao mesmo tempo (usando WLS2 - Windows Linux Subsystem).  
Se você tem uma máquina Windows, primeiro ative o WLS2, e depois instale git, nvm, NodeJS, e clasp no Linux embarcado.
Recomendamos usar o Linux Ubuntu 20.04 LTS embarcado no Windows 10/11. O Ubuntu 20.04 pode ser instalado baixando direto da Microsoft Store.  

3. **clonar o repositorio do Github (https://github.com/hrbsystems/googleAppScript-IW-Telemedicine-API):**  
Antes de tudo, criar um diretório temporário qualquer em sua maquina e se posicione nele usando o comando *cd*.  
Use o comando abaixo dentro do diretório temporário que foi criado:
```bash
git clone git@github.com:hrbsystems/googleAppScript-IW-Telemedicine-API.git
```  
> *Obs:  
Este commando acima só irá funcionar se a maquina tiver o git instalado e a chave pública ssh do usuário da maquina usada na instalção estiver cadastrada no github pelo suporte da Iberwan.    
(Essa chave publica é solicitada na etapa de pre-instalação).  
Informação de como gerar a chave publica está presente na Etapa 1 de pré-instalação.  
Se vc chegou até aqui é porque vc já deve ter cumprido essa exigencia. Caso não interrompa o processo de instalação nesse ponto e continue quando pronto.*  
3. **Usar comando linux *cd* para tornar o diretorio onde o repositorio foi clonado o diretório corrente:**  
```bash
cd googleAppScript-IW-Telemedicine-API
```  

4. **use o programa *clasp* (instalado no passo 1) para fazer login no Google word Spaces usando as credenciais do usuário infra criado com a finalidade de instalar o IW-Telemedicine-API.**  
```bash
clasp login  
```  
>Este comando deve ser executado no diretório do repositorio clonado.  
Use o usuário (normalmente um endereço de email) e sua respectiva.  
Somente o cliente tem essa informação.  
Normalmente a execução do comando *clasp login* causa a abertura de um Navegador, mostrando a página *OAuth* de autorização pedindo autorização para várias coisas.  
Todos os itens devem ser autorizados.  
Após autorizar, feche o Browser e continue os passos seguintes usando o terminal.  

  
5. Use o comando *create* do *clasp* para criar um projeto do tipo Web App associado a conta do usuário logado:  
```bash
clasp create --type webapp
```  

6. **Use o comando *push* do *clasp* para carregar todos os scripts presentes no diretorio corrente no *Google Workspace* do usuário:**
```bash
clasp push
```  
>Obs:  
Este comando usa uma série de infomações coletadas do ambiente que o usuário executou o comando.
como:  
Diretório corrente onde o comando foi dado que se tornará o nome do projeto dentro do Google Workspace do usuário.  
Dados do usuário logado e suas respectivas credenciais de acesso ao Google Workspace.  
Troca as extenções dos arguivos .js para .gs dentro do google work spaces. Somente a extensão.  
E outros detalhes relacionados ao google App Scripts.  

7. **Abrir no Navegador padrão o projeto que foi carregado no passo anterior já dentro do Google Work Space do usuário usado na instalação:**   
```bash
clasp open
```    
A execução do comando acima abre o IDE do Google App Script no navegador já devidamente posicionado no espaço do usuário.  

>Aqui termina a segunda etapa de instalação do IW-Telemedicina-API.  
A partir daqui, o usuário pode continuar a instalação na [Etapa 3](./installing-iw-telemedicine-in-clients-gas-ide-lang-pt.md) que é executada na tela do Navegador que acaba de ser aberta.  

