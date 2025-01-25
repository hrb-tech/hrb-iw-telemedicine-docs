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

## 1. **implantar o projeto:**  
Ao executar o ultimo passo da etapa anterior estaremos com o Navegador aberto no projeto do IW-Telemedicine-API que acaba de ser carregado.  
Clicar no botão azul *implantar (deploy)* localizado no topo do IDE e selecione a opção *gerenciar implantações (manage deployments)*:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-0.png)  
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-1-criar-implantacao.png)  
Aqui pressione o botão: *create Deployment (criar Implantação)*  
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-2-implantar.png)  
Presione o botão *Implantar (Deploy)*  
Na sequencia aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-3-autorizar-acesso.png)  
Clique no botão azul *Autorizar Acesso*.
Agora, uma série de telas associadas ao processo de autorização irão se suceder.
Não é recomendado mostrar todas essas telas aqui no procedimento porque a aparência delas mudam com frequência.
O Google está sempre mexendo nessas telas. Segurança é uma questão levada muito a sério.  

Ao final da implantação, aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-5-concluido.png)  

Essa tela oferece a possibilidade de copiar a URL BASE de acesso à aplicação.  
Essa URL é muito importante e deve ser guardada. Será usada em passos subsequentes.  
Não se preocupe caso não tenha salvo essa URL BASE. O IDE do Google App Scripts oferece recursos de consultar esse dado sempre que se desejar.   
  
**IMPORTANTE:**   
**Todas as vezes que se instala ou atualiza o IW-Telemedicine-API, é criada uma nova URL BASE**  

## 2. **criar uma propriedade de projeto chamada: AUTHORIZED_URL**  
Para tal, clicar na opção configurações (Settings) localizada do lado esquerdo do IDE.
Rolar a tela (para baixo) até encontrar a opção: *script properties (propriedades do script)*
Adicionar uma nova propriedade chamada: AUTHORIZED_URL e atribuir um valor aleatório qualquer inicialmente, ex: abdefg    
Essa propriedade será usada para validar a URL usada em todas as requisições HTTP para esta instância do IW-Telemedicina-API que acaba de ser instalada.  
Para efeito de testes ela foi incializada com valor incorreto de propósito.

3. **Fazer testes de chamadas da IW-Telemedicne-API inicialmente sem valor o correto (URL BASE) na propriedade AUTHORIZED_URL:**  
Fazer 4 testes usando os comandos abaixo.  
Cada teste usa uma linguagem de progração distinta para fazer as chamadas.
Garantem independência tecnológica dos serviços de telemedicina e o funcionamento da proteção de aceite apenas de chamadas que usam
a URL BASE certa de chamada.
Nesses testes a seguir o IW-Telemedicine-API rejeitará as chamadas, uma vez que a propriedade AUTHORIZED_URL foi inicialmente valorada com valor aleatório e portanto incorreto.  
**Esses testes são vitais para garantir que IW-Telemecine-API está acessivel a todos que sabem chamá-la de fato. E independente da tecnologia usada na chamada.**  
   
Linguagem Python:  
```bash  
python3 test-iw-telemedicine-api-call.py URL_BASE_CORRETA
```  
Nesse comando deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.  
A resposta deve ser:  
```json  

```

---  

Linguagem Node versão 20 (JavaScript):  
```bash  
node (WIP...) URL_BASE-CORRETA
```  
Nesse comando, também deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.  
**A resposta deve ser a mesma da chamda feita em Python.**  

---  

Linguagem Java 8:  
```bash  
java (WIP...) URL_BASE-CORRETA
```  
Nesse comando também deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.    
**A resposta deve ser a mesma da chamda feita em Python.**  

---  

Linguagem *Golang 1.21*:  
```bash  
test-iw-telemecine-api URL_BASE_CORRETA
```  
Nesse comando também deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.  
**A resposta deve ser a mesma da chamda feita em Python.**  


Agora siga para a Etapa 4: [Etapa 4](installing-iw-telemedicine-in-clients-iwcare-config-lang-pt.md)  

