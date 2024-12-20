# Etapa 4 da Instalação IW-Telemedicina-API:  

>Essa etapa é executada integralmente no Aplicatico Iw-Care.  
Por usuário que tenha acesso na configurações de parametros do Iw-Care.*(tela 151)*

1. Acessar o Iw-Care.
Fazer Login no Iw-Care com o usuário administrador.  

2. Acessar a tela 151:  

3. Procurar a propriedade: IW_TELEMEDICINE_API_URL  
Caso já exista, alterar o valor da propriedade para o valor da URL do Iw-Telemedicina-API.  
Caso não exista, adicionar a propriedade com o valor da URL do Iw-Telemedicina-API.  

4. salvar as propriedades. 

5. Fazer um teste de chamada a API do Iw-Telemedicina.  
Acessar as telas do Iw-Care que permitem acesso ao Iw-Telemedicina-API.  
A medida que o Sistema é evoluido e novas funcionalidades são implementadas, novas telas serão criadas para acesso a essas funcionalidades. Hoje as telas do Evoluções clínicas do Porntuário do IW-Care já oferecem acesso a essas funcionalidades.  

Posicione o Prontuário em um usuário de Testes (que não tenha impacto na produção) ou melhor, faça login um Iw-Care de treinamento ou de homologação caso existam. É o melhor modo de fazer testes sem impactar a produção.  
Crie Teleconsultas pata o Paceinte de testes.

Em seguida acesse o calendário do Google Workspace do usuário infra. Todas as teleconsultas criadas deverão aparecer no calendário do Google Workspace do usuário infra.  
NO calendario do Google Workspace do usuário infra, devrerá existir uma agenda para cada Médico que criou Teleconsultas.
E dentro da Agenda desse médico, deverá existir uma Teleconsulta para cada Teleconsulta criada.  

Esses testes são fundamentais para garantir que o Iw-Telemedicina-API está funcionando corretamente.  

**O IW-Telemedicina-API não pode ser considerado *Instalado* se esses testes não forem bem sucedidos.** 



Aqui termina a etapa 4 da instalação do Iw-Telemedicina-API. Que é a etapa final da instalação.  

**IMPORTANTE:**  
>*Agora o diretorio temporário de instalação deve ser excluido da máquina usada para instalar o Iw-Telemedicina-API.  
Nele estão fontes e outros aqruivos protegidos por direitos autorais.*  

---
**FIM.**


