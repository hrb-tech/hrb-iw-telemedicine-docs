# Procedimento de Pré-instalação do IW-TELEMEDICINE-API no Google Workspace do cliente.  

É pré-requisito para a instalação do IW-TELEMEDICINE-API no Google Workspace do cliente.  
Só pode ser executado por um usuário com "status" de Administrador do Google Workspace do cliente.  
*Todos os passos descritos aqui são de responsabilidade do cliente.*  
*A não disponibilização de qualquer dos passos impede a instalação do IW-TELEMEDICINE-API.*

1. Contratar Google Workspace do cliente:  
Cliente deve contratar o Google Workspace. (ou seja, assinar o serviço do Google Workspace).
O tipo de conta do Google Workspace mais simples atende o propósito do IW-TELEMEDICINE-API. (Conta tipo *Business Starter*)
Assinado o plano mais básico, já é automaticamente definido o *usuário Master* do Google Workspace do cliente.
Esse usuário só deve ser usado para a *criação do Work Space - assinatura* e outras tarefas críticas, como o cancelamento da assinatura por exemplo.  
O usuário também tem uma serie de outros privilégios como acesso completo ao console de administração do Google workspaces e acesso a dados de faturamento.
*Usuário Master jamais deve ser usado no dia a dia.*
É o único usuário com poderes para cancelar a assinatura do Google Workspace.  

**A assinatura do Google Workspace deve estar no estado ATIVA para que tenha início a instalação do IW-Telemedicina-API.** 

Obs:  
Se o cliente já possui assinatura do Google  Workspace, então o usuário Master já existe. 
E o cliente deve verificar se a conta está ativa.  
A conta estando suspensa, mesmo que existente, impede a instalação do IW-Telemedicina-API.
Um pequeno atraso ou irregularidade no pagamento mensal por exemplo pode resultar em suspenção da conta.

2. Criar usuário adicional infra@<customer-domain> no Google Workspace do cliente:  
Usar o acesso do usuário Master para criar o usuário infra@<customer-domain> no Google Workspace do cliente.  
O usuário infra@<customer-domain> é o usuário que será usado para instalar a IW-Telemedicina-API.  
O cliente tem liberdade para definir o nome que bem enteder para esse usuário.  
Sugerimos o nome infra@<customer-domain> apenas para manter nossas instalações padronizadas. (substituir <customer-domain> pelo domínio do cliente)  

É impressindível a criação desse usuário. Ele é *pivot* para todas as integrações com o sistema IW-Care.  
**Sem a existencia desse usuário não é possível instalar a IW-Telemedicina-API.**  

Esse usuário extra implica em custos adicionais para o cliente (aprox. $US 5 a $US 7 por mês para contas do tipo *Business Starter*)    
Conferir junto ao Google os preços atualizados, mas não devem fugir muito desses valores.  
É o único custo que o IW-Telemedicina-API acrescenta além da assinatura básica da plataforma Google Workspace.  

Ao criar o usuário infra@<customer-domain>, o cliente deve definir uma senha para ele.  
A senha deve ser forte e segura.  
O usuário infra@<customer-domain> deve ter acesso a todos os recursos do Google Workspace do cliente.  
(principalmente Gmail, Calendar, Drive, Meet, Sheets, Docs)

3. Autorizar o usuário infra@<customer-domain> a receber requisições via *Google App Script API* dentro so seu Workspace:  
Só o próprio usuário infra@<customer-domain> pode autorizar o acesso ao seu próprio Workspace via *API Google App Script*. 
Todas as comunicações no momento de instalação do IW-Telemedicina-API são feitas via *API Google App Script*. (uma API interna do Google)  
Todos os comandos *clasp* executados na segunda estapa da instalação são feitos via *API Google App Script*.
A ausência dessa autorização impede a instalação da IW-Telemedicina-API.
Para autorizar o usuário infra@<customer-domain> a receber requisições via Google App Script API, o usuário infra deve:  
* acessar o link: https://script.google.com/home/usersettings 
* e ligar a chave "Allow scripts to run on your domain".

5. Assinar o BBA:  
O cliente deve assinar o BBA (Basic Business Associate) do Google Workspace.
O BBA é um termo de compromisso que o Google axige de todos os clientes para que os clientes possam usar o Google Workspace em seus negócios. Principalmente em conteúdos relacionados a saúde.  
Em resumo, trata-se de um contrato que permite que o Google armazene dados pessoais de seus clientes, desde que esses dados sejam usados apenas para fins de negócios e em conformidade com as leis e regulamentos aplicáveis (HIPAA, GDPR, etc.).
Todos os serviços do Google Workspace que o IW-TELEMEDINA-API usa são implementados em conformidade com a HIPAA e GDPR.
O IW-Telemedicina-API não armazena nenhum dado pessoal sensível do Usuário, dos Pacientes ou de profissionais de saúde. Nem mesmo em trânsito esses dados são usados. Usa HTTPS para comunicação segura.  
Esse termo de compromisso é a garania para o google de que as empresas usuárias do Google Workspaces não vão usar o Google Workspace para fins ilegais ou que agridam alguma diretriz da HIPAA ou GDPR.  

**Como assinar o BBA?**  
Na console de administração do Google Workspace, o cliente deve acessar a aba "Segurança" e clicar em "BBA".
Use o usuário Master do Google Workspace do cliente para assinar o BBA.  


6. Autorizar a máquina que será usada para instalar a IW-Telemedicina-API no Google Workspace do cliente:  
É necessário que a máquina que será usada para instalar a IW-Telemedicina-API no Google Workspace do cliente tenha acesso a internet e acesso ao Google Workspace do cliente. Em ressumo qualquer máquina com acesso a internet e que tenha um Navegador Web pré-instalado (preferível Google Chrome). Recomendamos que seja uma maquina **Linux**, porque simplifica a instalação e manutenção. Maquinas com MacOS (Apple) também podem ser usadas com as mesmas facilidades, embora não testado. Máquinas Windows podem ser usadas, mas será necessário instalação de software adicional e configurações extras.  
A etapa 2 de instalação do IW-Telemedicina-API fluirá de modo mais suave em máquinas linux. Para todas as demais etapas de instalação, o sistema operacional não importa. 

>Obs Apenas para máquinas Windows, sabe-se:  
* É necessário instalar o Google Chrome.
* Habilitar o WLS2 para Windows.  
* Instalar o WSL2 e o Ubuntu 20.04 LTS.  

>Microsoft disponibiliza o uso do Linux ao mesmo tempo que o Windows.  
Com o WLS2, o Windows passa a ser um sistema operacional com Linux embarcado.  
O WSL2 permite a execução de aplicações Linux diretamente no Windows.  
todos os comandos da etapa 2 de instalação do IW-Telemedicina-API podem ser executados em um terminal do WSL2.
Usar o WLS2 é a nossa recomendação para quem só pode usar uma maquina Windows.
Existem outras formas de usar Linux dentro de máquinas windows, mas o WSL2 é a mais simples e tem a vantagem de ter um terminal do Linux dentro do Windows. O WLS2 é uma tecnogia que a Microsoft vem desenvolvendo a mais de uma década e hoje se encontra em sua versão 2 e com  boa maturidade. Está disponivel em maquinas Windows 10 e Windows 11.   



**IMPORTANTE:**  
> Dados da máquina que será usada para instalar a IW-Telemedicina-API devem ser informados a Ibewan.  
Esses dados se resumem em passar uma chave publica rsa gerada por um programa muito comum em maquinas linux chamado *sshkey-gen*.  
recomenda-se enviar essa chave por email para o suporte da Iberwan que providenciará os devidos acessos.  
Após o termino bem sucedido da instalação, essa chave publica rsa será removida. Qulaer nova instalação ou atualização da IW-Telemedicina-API deverá ser gerada uma nova chave publica rsa.  

[procedimento para gerar a chave publica rsa](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04)


7. Assinar o termo de sigilo da Iberwan
O cliente deve entrar em contato com o suporte da Iberwan para assinar o termo de sigilo.



O **Cliente** tendo providenciado todos os itens acima, pode passar para a etapa 2 de Instalação do IW-Telemedicina-API.  
[Etapa 2 de inatalação Iw-Telemedicine-API](installing-iw-telemedicine-in-clients-clasp-cli-lang-pt.md)

