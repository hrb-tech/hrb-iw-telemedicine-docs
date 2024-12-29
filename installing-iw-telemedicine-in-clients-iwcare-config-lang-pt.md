# Etapa 4  
## Instalação IW-Telemedicina-API  
  

>Essa etapa é executada integralmente no Aplicatico Iw-Care.  
Por usuário que tenha acesso na configurações de parametros do Iw-Care.*(tela 151)*

1. **Acessar o IW-Care:**  
Fazer Login no IW-Care com o usuário administrador.  

2. **Acessar a tela 151:**  

3. **Procurar a propriedade: IW_TELEMEDICINE_API_URL**  
Caso já exista, alterar o valor da propriedade para o valor da URL base do IW-Telemedicina-API, gerada na etapa anterior.  
Caso não exista, adicionar a propriedade com o valor da URL do Iw-Telemedicina-API, gerada na etapa anterior.    

4. salvar as propriedades. 

5. Fazer um teste de chamada a API do IW-Telemedicina.  
Acessar as telas do IW-Care que permitem acesso ao Iw-Telemedicina-API.  
A medida que novas versões do IW-Care são disponiblizadas i, novas telas serão criadas para acesso a telemedicina.
Hoje as telas do Evoluções clínicas do Prontuário do IW-Care já oferecem acesso a essas funcionalidades.  

Posicione o Prontuário em um usuário de Testes (que não tenha impacto na produção) ou melhor, faça login um IW-Care numa base de treinamento ou de homologação caso existam.  
É o melhor modo de fazer testes sem impactar a produção.  
Crie Tele-consultas para o Paciente de testes.

Em seguida acesse o calendário do Google Workspace do usuário infra respectivo.  
Todas as tele-consultas criadas deverão aparecer no calendário do Google Workspace do usuário infra.  
Na aplicação de Calendário do Google Workspace do respectivo usuário infra, deverá existir uma agenda para cada Médico que criou Tele-consultas.
E dentro da Agenda desse médico, deverá existir uma Tele-consulta para cada Tele-consulta criada.  

Esses testes são fundamentais para garantir que o IW-Telemedicina-API foi instalado corretamente está funcionando bem.  

**O IW-Telemedicine-API não pode ser considerado *Instalado* se esses testes não forem bem sucedidos.** 


Aqui termina a etapa 4 da instalação do Iw-Telemedicina-API. Que é a etapa final da instalação.  

**IMPORTANTE:**  
>*Agora o diretório temporário de instalação deve ser excluído da máquina usada para instalar o IW-Telemedicine-API.  
Nele estão fontes e outros arquivos protegidos por direitos autorais.*  

---
**FIM.**


