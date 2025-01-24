# Etapa 2  
## Instalação IW-Telemedicine no Google Workspace da Iberwan
É recomendavel usar Linux (Ubuntu 22.04) durante toda a Etapa 2.  
Diversos programas que serão instalados nessa etapa para completar o ambiente de instalação foram escritos pensando-se em Linux/Mac.
Máquinas windows podem ser usadas, mas necessitam de pacotes/configurações adicionais.  

> Somente para máquinas Windows:
Windows 10/11 oferece recurso de uso do Linux e Windows ao mesmo tempo (usando WLS2 - Windows Linux Subsystem).  
Se você tem uma máquina Windows, ative o WLS2 e instale da loja da Microsoft o Linux Ubuntu 22.04
Instale o navegador Chrome no windows. O navegador Edge que vem nativamente com o Windows irá acusar erros.
Recomendamos usar o Linux Ubuntu 22.04 LTS embarcado no Windows 10/11. O Ubuntu 22.04 pode ser instalado baixando direto da Microsoft Store

1. **instalar o git:**
```bash
sudo apt-get update && sudo apt install -y git
```   

2. Criar um direotrio temporário onde todos os trabalhos de instalação serão executados.  
Sugerimos o nome "IW-Telemedicine-API-install-tmp" para esse diretório. Mas pode ser qualquer nome. 

3. **clonar o repositório do Github (https://github.com/hrbsystems/googleAppScript-IW-Telemedicine-API):**  
Antes, como já orientado no passo anterior, criar um diretório temporário qualquer em sua maquina e se posicione nele usando o comando *cd*.  
Use o comando abaixo dentro do diretório temporário que foi criado:
```bash
git clone git@github.com:hrbsystems/googleAppScript-IW-Telemedicine-API.git
```  
> *Obs:  
Este commando clone acima só irá funcionar se a sua máquina tiver o git instalado e a chave pública ssh do seu usuário estiver cadastrada no github pelo suporte da Iberwan.    
(Essa chave publica é criada na etapa 1 (pre-instalação).  
Informação de como gerar a chave publica está presente na Etapa 1.  
Se vc chegou até aqui é porque vc já deve ter cumprido essas exigências. Caso não, interrompa o processo de instalação nesse ponto e continue quando pronto.*
  
4. **Usar os comandos linux a seguir :**  
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
cd googleAppScript-IW-Telemedicine-API_${TAG}
```

Esta sequencia deve ser execurada uma linha de cada vez. Elas farão:  
* Posicionamento do diretorio do projeto clonado como diretorio corrente.  
* Obtenção a Tag mais recente do branch corrente (branch main)
* posiciona no diretorio pai
* troca o nome do diretrio do projeto clonado, incluindo no nome do mesmo a tag como sufixo (adequação ao padrao de instalação)
* reposiciona no diretorio filho (do projeto clonado).  
O nome final do diretório clonado ficaria: googleAppScript-IW-Telemedicine_API_v1.2.3 (assumindo que a ultima tag é v1.2.3)

IMPORTANTE: todos os passos do procedimento possuem uma razão de ser e em especial, essa sequencia de comandos acima.  
Tem haver com nossos padrões de instalação.  
Todas as versões do IW-Telemedicine_API devem obrigatoriamente serem instaladas com um sufixo que identifique precisamente a versão da mesma.
Sem isso, devemos reiniciar do zero tudo. Faz parte da boa documentação da instalação. Embora possa parecer radical iniciar do zero, a execução de
tudo que antecede é rápida.  
  

5. Excute o script *_prepare-basic-ubuntu-env.sh*     
   ```bash
   ./_prepare-basic-ubuntu-env.sh
   ```
   Esse comando irá instalar uma serie de pacotes do Ubuntu 22.04 necessários à instalação da Iw-Telemedicine-API.
   Sem eles a instalação não pode prosseguir.
   
5. **use o programa *clasp* (instalado no passo anterior) para fazer login no Google Workspace usando as credenciais do usuário criado com a finalidade de instalar o IW-Telemedicine-API.**  
```bash
clasp login  
```  
>Este comando deve ser executado no diretório do repositório clonado. Deixe apenas 1 instância do Navegador Chrome aberta antes de executar o clasp login.
**MUITO CUIDADO:**A existência de multiplas instâncias (janelas) do Nevegador Chrome pode criar confusão. Cada uma pode estar logada in um usuário distinto no Google Workspace.**  
Normalmente a execução do comando *clasp login* causa a abertura de uma aba no Navegador, mostrando a página *OAuth* de autorização pedindo autorização para várias coisas.  
A conta <nome_cliente>@iwsoftware.com.br deve ser selecionada e TODOS os itens devem ser autorizados.  
Após autorizar, feche apenas a aba do Browser usada pelo login e continue os passos seguintes usando o terminal.  

6. Habilitar o uso da Google-Appscript-API na conta do <nome_cliente>@iwsoftware.com.br do Google Workspace da Iberwan:
Após o clasp login executado no passo anterior, o navegador chrome já deve estar logado corretamente na conta <nome_cliente>@iwsoftware.com.br  
Para habilitar o uso da API do Google, acesse https://script.google.com/home/usersettings no navegador que está logado na respectiva conta e habilite colocando em ON o respectivo flag  
Se vc habilitou agora o flag, espere uns poucos minutos para que essa habilitação seja propagada dentro do infra do Google.
Caso esse flag ainda não esteja habilitado ou mesmo não propagado, o comando seguinte retornará um erro, informando a necessidade dessa habilitação.
nesse caso o comando clap create --type webapp deve ser repetido um tempo depois para que o projeto App Script possa ser criado de fato no Google workspace.
  
7. Use o comando *create* do *clasp* para criar um projeto do tipo Web App associado a conta do usuário logado:
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
Troca as extenções dos arguivos .js para .gs dentro do projeto no Google Workspace. Somente a extensão.
Não sobe para o Google Workspace arquivos que não dizem respeito a Projetos Google App Script e que por ventura estejam presentes no diretório raiz do repo clonado
E outros detalhes relacionados ao google App Scripts.  São muitos detalhes que o clasp faz automaticamente.

7. **Abrir no Navegador padrão o projeto que foi carregado no passo anterior já dentro do Google Work Space do usuário usado na instalação:**   
```bash
clasp open
```    
A execução do comando acima abre o *IDE do Google App Script* no navegador e já devidamente posicionado no espaço do usuário infra@ e no Projeto que foi instalado.    

>Aqui termina a segunda etapa de instalação do IW-Telemedicina-API.  
A partir daqui, o usuário pode continuar a instalação na [Etapa 3](./installing-iw-telemedicine-in-clients-gas-ide-lang-pt.md) que é executada na tela do Navegador que acaba de ser aberta.  

