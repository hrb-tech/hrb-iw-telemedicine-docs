# Procedimento de Pré-instalação do IW-TELEMEDICINE-API - Google Workspace da Iberwan.  

1. Criar usuário adicional infra.<custopmer_name>@iwsoftware.com.br no Google Workspace do cliente:  
Usar o acesso do usuário Master para criar o usuário infra.<customer_name>@iwsoftware.com.br no Google Workspace da Iberwan.  
O usuário infra.<Customer_Name><>@iwsoftware.com.br é o usuário que será usado para instalar a IW-Telemedicina-API para o client específico.
(Substituir <Customer_Name> pelo nome da empresa cliente).    

É impressindível a criação desse usuário. Ele é o *pivot* para todas as integrações IW-Telemedicine-API com o sistema IW-Care em um cliente.  
**Sem a existência desse usuário não é possível instalar a IW-Telemedicina-API.** para um cliente.  

Ao criar o usuário infra.<Customer_Name>@iwsoftware.com.br, deve-se definir uma senha para ele.  
A senha deve ser forte e segura.  
Esse usuário deve ter acesso a todos os recursos do Google Workspace da Iberwan.  
(principalmente Gmail, Calendar, Drive, Meet, Sheets, Docs)

2. **Autorizar o usuário infra.<Customer_Name>@iwsoftware.com.br a receber requisições via *Google App Script API* dentro so seu Workspace:**  
Só o próprio usuário infra@<customer-domain> pode autorizar o acesso ao seu próprio Workspace via *API Google App Script*. 
Todas as comunicações no momento de instalação do IW-Telemedicina-API são feitas via *API Google App Script*. (uma API interna do Google)  
Todos os comandos *clasp* executados na segunda estapa da instalação são feitos via *API Google App Script*.
A ausência dessa autorização impede a instalação da IW-Telemedicina-API na conta do usuário criado para o cliente dentro do Workspace da Iberwan.  
Para autorizar o usuário infra.<Customer_Name>@iwsoftware.com.br a receber requisições via *Google App Script API*, o usuário infra deve:
* Fazer login no *Google Workspace da Iberwan*  
* Acessar o link: https://script.google.com/home/usersettings 
* E ligar a chave "Allow scripts to run on your domain".


3. **Autorizar a máquina que será usada para instalar a IW-Telemedicina-API no Google Workspace da Iberwan:  
A máquina pessoal do profissional da Iberwan que vai instalar/atualizar a IW-Telemedicine-API precisa autorizar a sua máquina a acessar o repositório onde se encontram os fontes da IW-Telemedicine-API.  
Essa autorização só precisa ser feita uma unica vez para um dado profissional. Deve ser repetida apenas nos casos onde o profissional trocar de máquina, ou quando o mesmo não for mais executar instalações/atualizações.
(Ex: desligamento da Iberwan, mudança de atribuições, etc).  
 
> É necessário que a máquina tenha um bom e estável acesso a internet e um Navegador moderno instalado (preferível Google Chrome).
Recomendamos também que seja uma maquina **Linux**, porque simplifica a instalação e manutenção. Maquinas com MacOS (Apple) também podem ser usadas com as mesmas facilidades, embora não testado.
> Máquinas Windows podem ser usadas, mas será necessário instalação de software adicional e configurações extras.  
A etapa 2 de instalação do IW-Telemedicina-API fluirá de modo mais suave em máquinas linux. Para todas as demais etapas de instalação, o sistema operacional não importa.  

>Obs Apenas para máquinas Windows, sabe-se:  
* É necessário instalar o Google Chrome. O Navegdor nativo do windows costuma apresentar erros em alguns casos. Motivos desconhecidos.
* Habilitar o WLS2 para Windows.  
* Instalar o WSL2 e o Ubuntu 20.04 LTS.  
A Microsoft disponibiliza o uso do Linux ao mesmo tempo que o Windows.  
Com o WLS2 (Windows Linux Subsystem), o Windows pode ter um sistema operacional Linux *embarcado*.
 
>Todos os comandos da etapa 2 de instalação do IW-Telemedicina-API podem ser executados em um terminal do WLS2.
Usar o WLS2 é a nossa recomendação para quem só pode usar uma maquina Windows.
Existem outras formas de usar Linux dentro de máquinas windows, mas o WLS2 é a mais simples e tem a vantagem de ter um terminal do Linux dentro do Windows.
>O WLS2 é uma tecnogia que a Microsoft vem desenvolvendo a mais de uma década e hoje se encontra em sua versão 2 e com boa maturidade.
>Está disponivel para todas as máquinas com Windows 10/11.   



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

