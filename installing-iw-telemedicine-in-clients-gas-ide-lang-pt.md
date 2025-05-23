# Etapa 3  
## Instalação IW-Telemedicina-API
  
Executada no início usando o IDE do Google para App Scripts que funciona direto do Navegador (Google Chrome de preferência)  
  
>Essensialmente, os passos abaixo irão realizar todas as autorizações de execução dos scripts como se fossem dispadodos pelo usuário da respectiva conta (<nome_cliente@iwsoftware.com.br>),
permitindo que os scripts do projeto carregados na etapa anterior sejam acessados na internet e também tenham acesso aos recursos necessários do Google Workspace.  
Essas autorizações são *essenciais* para que o projeto funcione e sejam acessados via internet.  
Além disso, será definida uma propriedade de projeto que será usada para validar a URL usada em todos as requisições HTTP
para a instância do IW-Telemedicina instalada no cliente  

Seguem os passos:  

## 1. **implantar o projeto:**  (no IDE)
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
Não vamos mostrar aqui todas essas telas de autorização porque a aparência delas muda com frequência.
O Google está sempre alterando elas. Segurança é uma questão levada muito a sério.  
**O importante é autorizar tudo o que for perguntado.**  

Ao final da implantação, aparecerá a tela abaixo:  
![manage deployments dialog](./Screenshot-gas-gerenciar-implantacao-5-concluido.png)  

Essa tela oferece a possibilidade de copiar a URL BASE de acesso à aplicação.  
Essa URL é muito importante e deve ser guardada. Será usada em passos subsequentes.  
Não se preocupe caso não tenha salvo essa URL BASE. O IDE do Google App Scripts oferece recursos de consultar esse dado sempre que se desejar.   
  
**IMPORTANTE:**   
**Todas as vezes que se instala ou atualiza o IW-Telemedicine-API, é criada uma nova URL BASE**  

## 3. Fazer TESTES de chamadas da API: (no terminal)  

Fazer 3 testes usando os comandos abaixo no terminal.  
  
**IMPORTANTE:** executar esses comandos no direotiro: *<diretorio-temporario>/googleAppScript-IW-Telemedicine-API_<TAG>/api-call-tests/*   
Cada comando de teste usa uma linguagem de programação distinta para fazer a chamada.  
Garantem independência tecnológica dos serviços de telemedicina.  
Nesses testes o IW-Telemedicine-API aceitará as chamadas.    
**Esses testes são vitais para garantir que API está acessivel somente aos que sabem chamá-la de fato. E independente da tecnologia usada na chamada.**  
A sequir os comandos que devem ser usados.    
  
**Linguagem Python 3.10:**  
```bash  
python3 test-iw-telemedicine-api-call.py URL_BASE_CORRETA
```  
>Nesse comando deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.

A resposta deve o padrão abaixo:  
```json  
{
  "responseCode": 0.0,
  "iwResponseData": {
    "apiName": "IW-Telemedicine-API for Google Meeting",
    "apiVersion": "1.1.0"
  }
}
```
Prestar atenção ao valor do campo *apiVersion* na resposta.
Se o valor for diferente da versão que estamos instalando significa que a API não está funcionando corretamente.

---  

**Linguagem Java 8:**  
```bash
java -cp ".:gson-2.11.0.jar" testIwTelemedicineApiCall URL_BASE_CORRETA 
```  
>Nesse comando também deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.
**A resposta deve ser a mesma da chamda feita em Python.**  

---  

**Linguagem Golang 1.21:**  
```bash  
./testIwTelemedicineApiCall URL_BASE_CORRETA
```  
>Nesse comando também deve-se substituir *URL_BASE_CORRETA* da instalação, salva no final do passo 1.  
**A resposta deve ser a mesma da chamda feita em Python.**  


Agora siga para a Etapa 4: [Etapa 4](installing-iw-telemedicine-in-clients-iwcare-config-lang-pt.md)  

