# Etapa 4  
## Instalação IW-Telemedicina-API  
  

>Essa etapa é executada integralmente no Aplicatico Iw-Care,  
por usuário que tenha acesso na configurações de parametros do Iw-Care.*(Tela 151)*

1. **Acessar o IW-Care:**  
Fazer Login no IW-Care com o usuário administrador.  

2. **Acessar a tela 151:**  

3. **Procurar a propriedade: GLB_TELEMEDICINE_URL**  
Caso já exista, alterar o valor da propriedade para o valor da URL BASE do IW-Telemedicina-API, gerada na etapa anterior.  
Caso essa peopriedade ainda não exista no IW, adicionar a propriedade e valore ela com o valor da URL gerada na etapa anterior.    

4. Salvar as propriedades. 

5. Fazer um teste de chamada a API do IW-Telemedicina no Banco de treinamento ou de homologação
Acessar as telas do IW-Care que permitem acesso ao Iw-Telemedicina-API.  
A medida que novas versões do IW-Care são disponiblizadas, novas telas serão criadas para acesso a telemedicina.
Hoje as telas de Evoluções clínicas do Prontuário já oferecem esse acesso.  

Posicione o Prontuário em um usuário de Testes (que não tenha impacto na produção) ou melhor, suba o IWCare fazendo login em uma base de treinamento ou de homologação caso existam.  
É o melhor modo de fazer testes sem impactar a produção.  
Crie Tele-consultas para o Paciente de testes.

Em seguida acesse o calendário do Google Workspace do usuário <nome_cliente>@iwsoftware.com.br  
Todas as tele-consultas criadas deverão aparecer no calendário do Google Workspace do usuário.  
Na aplicação de Calendário do usuário, deverá existir uma agenda para cada Médico para o qual criou-se Tele-consultas.
E dentro da Agenda desses médicos, deverá existir um evento para cada Tele-consulta criada.  

Esses testes são fundamentais para garantir que o IW-Telemedicina-API foi instalada corretamente está funcionando bem.e o IwCare está cnseguindo acessá-la.  

**O IW-Telemedicine-API não pode ser considerado *Instalado* se esses testes não forem bem sucedidos.** 


Aqui termina a etapa 4 da instalação do Iw-Telemedicina-API. Que é a etapa final da instalação.  

**IMPORTANTE:**  
>*Agora o diretório temporário de instalação pode ser excluído.  
Nele estão fontes e outros arquivos protegidos por direitos autorais.*  

---
**FIM.**


