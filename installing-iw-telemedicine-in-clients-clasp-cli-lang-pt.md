# Etapa 2  
## Instalação IW-Telemedicine no Google Workspace da Iberwan


1. **instalar os seguintes apps: git, nvm (node versions manager), NodeJS (latest 20), clasp (latest 2.4.2)**  
Todos esses progranas podem ser instalados em qualquer Sistema Operacional (Windows, Linux, MacOS).  
É recomendado usar Linux porque os apps de linha de comando como esses, normalmente foram escritos pensando-se em Linux.  
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
3. **Usar os comandos linux a seguir :**  
```bash  
cd googleAppScript-IW-Telemedicine-API
```
```bash
TAG=$(git describe --tags --abbrev=0)
```  
```bash  
cd ..
```
```bash  
mv googleAppScript-IW-Telemedicine-API googleAppScript-IW-Telemedicine-API_${TAG}
```

```bash
git clone git@github.com:hrbsystems/googleAppScript-IW-Telemedicine-API.git && \
cd googleAppScript-IW-Telemedicine-API && \
TAG=$(git describe --tags --abbrev=0) && \
cd .. && \
mv googleAppScript-IW-Telemedicine-API googleAppScript-IW-Telemedicine-API_${TAG} && \
cd googleAppScript-IW-Telemedicine-API_${TAG}

```


Esta sequencia deve ser execurada uma linha de cada vez. Elas farão:  
* Posicionamento do diretorio do projeto clonado como diretorio corrente.  
* Obtenção a Tag mais recente do branch corrente (branch main)
* troca o nome do diretrio do projeto clonado, incluindo no nome do mesmo a tag como sufixo (adequação ao padrao de instalação)  
O nome final do diretório ficará: googleAppScript-IW-Telemedicine_API_v1.2.3 (assumindo que a ultima tag é v1.2.3)

IMPORTANTE: todos os passos do procedimento possuem uma razão de ser e em especial, essa sequencia de comandos acima, tem haver com nossos padrões de instalação.  
Todas as versões do IW-Telemedicine_API devem obrigatoriamente serem instaladas com um sufixo que identifique precisamente a versão da mesma.
Sem isso, devemos reiniciar do zero tudo. Faz parte da boa documentação da instalação.
 
4. Mude para o diretorio do repositorio clonado no passo anterior:
   ```bash
   cd googleAppScript-IW-Telemedicine-API_${TAG}
   ```
   
5. **use o programa *clasp* (instalado no passo 1) para fazer login no Google word Spaces usando as credenciais do usuário infra criado com a finalidade de instalar o IW-Telemedicine-API.**  
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
**IMPORTANTE*: antes de dar esse comando é ncessario habilitar o uso da Google-AppScript-API na conta <nome-cliente>@iwsoftware.com.br no google workspace da Iberwan.
Para fazer isso acesse https://script.google.com/home/usersettings no navegador que está logado na respectiva conta e habilite colocando em ON o respectivo flag
se vc habilitou o flag recentemente, espere uns poucos minutos para que essa habilitação seja propagada dentro do infra do Google.
Caso esse flag ainda não esteja habilitado ou mesmo não propagado ainda na infra do Gooogle, o comando abaixo retornará um erro, informando a necessidade dessa habilitação.
nesse caso o comando deve ser repetido um tempo depois para que o projeto App Script possa ser criado de fato na respectiva conta.
   
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
A execução do comando acima abre o *IDE do Google App Script* no navegador e já devidamente posicionado no espaço do usuário infra@ e no Projeto que foi instalado.    

>Aqui termina a segunda etapa de instalação do IW-Telemedicina-API.  
A partir daqui, o usuário pode continuar a instalação na [Etapa 3](./installing-iw-telemedicine-in-clients-gas-ide-lang-pt.md) que é executada na tela do Navegador que acaba de ser aberta.  

