# Etapa 3  
## Instalação IW-Telemedicina-API
  

Executada usando o IDE do Google para App Scripts que funciona direto do Navegador (Google Chrome de preferência)  
*Esses passos devem ser executados pelo cliente, com suporte de um consultor da Iberwan se o cliente assim o desejar.*
  
>Essensialmente, os passos abaixo irão realizar todas as autorizações de execução dos scripts como se fossem dispadodos pelo usuário da respectiva conta (<nome_cliente@iwsoftware.com.br>),
permitindo que os scripts do projeto carregados na etapa anterior sejam acessados na internet e também tenham acesso aos recursos necessários do Google Workspace.  
Essas autorizações são *essenciais* para que o projeto funcione e sejam acessados via internet.  
Além disso, será definida uma propriedade de projeto que será usada para validar a URL usada em todos as requisições HTTP
para a instância do IW-Telemedicina instalada no cliente  

Seguem os passos:  


1. **implantar o projeto:**  
Ao executar o ultimo passo da etapa anterior estaremos com o Navegador aberto no projeto do IW-Telemedicine-API carregado no Google Workspace do usuário infra correspondente.
Clicar no botão *implantar (deploy)* e selecione a opção *manage deployments (gerenciar implantações)*    
em seguida aparecerá a caixa de Diálogo abaixo:
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-0.png)  
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-1-criar-implantacao.png)  
Aqui pressione o botão: *create Deployment (criar Implantação)*  
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-2-implantar.png)
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-3-autorizar-acesso.png)
Clique no botão azul Autorizar.  
Na sequnêcia uma série de telas associadas ao processo de autorização irão se suceder.
Não é recomendado exibir todas essas telas aqui no procedimento porque a aprencia dessas telas mudam com frequência.
O Google está sempre mexendo nessas telas, pois segurança é uma questão levada muito a sério por ele.  

Ao final da implantação (Deployment), aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-5-concluído.png)  

Essa tela oferece a possibilidade de copiar a URL BASE de acesso a aplicação.  
Essa URL é muito importante e deve ser guardada. Será usada em passos subsequentes.  
Não se preocupe caso não tenha salvo essa URL. O IDE do Google App Scripts oferece recursos de consultar esse dado sempre que se desejar.   
  
**IMPORTANTE:**   
**Todas as vezes que se instala ou atualiza o IW-Telemedicine-API, é criada uma nova URL BASE**  
**No próximo passo e também na estapa 4, essa URL será usada.**  

2. **criar uma propriedade de projeto chamada: AUTHORIZED_URL**  
Clicar na opção configurações (Settings) localizada do lado esquerdo do IDE.
Rolar a tela (para baixo) até encontrar a opção: *script properties (propriedades do script)*
Adicionar uma nova propriedade chamada: AUTHORIZED_URL e atribuir o valor da URL copiada da etapa anterior.  
Prestar muita atenção na digitação do nome da propriedade, com todas as letras maiúsculas.

Essa propriedade será usada para validar a URL usada em todas as requisições HTTP para esta instância do IW-Telemedicina-API que acaba de ser instalada.  
**È muito importante que essa propriedade seja corretamente valorada.**  
*Sem essa propriedade corretamente valorada, o IW-Telemedicina-API rejeitará todas as chamadas.*

3. **Fazer testes de chamadas da IW-Telemedicne-API:**  
fazer 6 testes usando os comandos abaixo. Cada teste usa uma linguagem de progração distinta para fazer as chamadas.
Os 2 comandos abaixo usam a linguagem Python  
```bash  
python3 test-iw-telemedicine-api-call.py URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR
```  
Nesse comando deve-se substituir URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR pela URL BASE da instalação.
A resposta deve ser algo como:  
```json  

```  
```bash  
python3 test-iw-telemedicine-api-call.py fakeURL
```  
Nesse comando deve-se substituir a palavra *fakeURL* por qualquer sequência de caracteres de tamnho 3 no mínimo. Ex: abc
A resposta deve ser algo como:  
```json  

```  
Os 2 comandos sequintes usam a linguagem java 8:  
```bash  
java -jar (WIP...) URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR
```  
Nesse comando deve-se substituir URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR pela URL BASE da instalação.
A resposta deve ser algo como:  
```json  

```  
```bash  
java -jar (WIP...) fakeURL
```  
Nesse comando deve-se substituir a palavra *fakeURL* por qualquer sequência de caracteres de tamnho 3 no mínimo. Ex: abc
A resposta deve ser algo como:  
```json  

```  

Os 2 comandos sequintes usam a linguagem Golang 1.21:  
```bash  
test-iw-telemecine-api URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR
```  
Nesse comando deve-se substituir *URL_DO_IW-TELEMEDICINE-API-SALVA-PASSO-ANTERIOR* pela URL BASE da instalação.
A resposta deve ser algo como:  
```json  

```  
```bash  
test-iw-telemecine-api fakeURL
```  
Nesse comando deve-se substituir a palavra *fakeURL* por qualquer sequência de caracteres de tamanho 3 no mínimo. Ex: abc
A resposta deve ser algo como:  
```json  

```
Esses testes são vitais para garantir que IW-Telemecine-API está acessivel a todos que sabem chamá-la de fato.
Independente da tecnolgia usada na chamada.

>Agora siga para a Etapa 4 da instalação do IW-Telemedicine-API:  
[Etapa 4](installing-iw-telemedicine-in-clients-iwcare-config-lang-pt.md)

