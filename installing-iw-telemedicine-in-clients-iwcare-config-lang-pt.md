# Etapa 4  
## Instalação IW-Telemedicina-API  
## COnfiguração final e testes de Integração

>Essa etapa é executada integralmente no Aplicatico Iw-Care,  
por usuário que tenha acesso a configurações de parametros do Iw-Care.*(Tela 151)*

1. **Acessar o IW-Care:**

> *Prefernciacialmente acessando um banco de treinamento ou de homologação. Na ausência desses bancos pode-se o banco de produção sem problemas
> uma vez que por arquitetura da telemedicina o IWCare é apenas uma app cliente da API de telemedicina que está em outro ambiente muito diferente (nuvem do Google).  

Fazer Login no IW-Care com o usuário administrador e que a nivel de IW seja considerado um médico com acesso ao prontuário.


3. **Acessar a tela 151:**  

4. **Procurar a propriedade: GLB_TELEMEDICINE_URL**  
Caso já exista, altere o valor da propriedade para o valor da URL BASE do IW-Telemedicina-API, gerada na etapa anterior - passo 1.  
Caso essa propriedade ainda não exista no IW, adicione a propriedade e valore a mesma adequadamente.    
E Salve as propriedades.

7. **Fazer varios testes de video-chamandas
Acessar as telas do IW-Care que permitem acesso à Iw-Telemedicina-API.  
A medida que novas versões do IW-Care são disponibizadas, novas telas serão criadas para acesso a telemedicina.
Hoje apenas as telas de Evoluções clínicas do Prontuário já oferecem esse acesso.  
Simule a criação de varias teleconsultas bem como a realização das mesmas.
Caso não saiba como usar essas telas, consulte o manual do IWCare.  

Posicione o Prontuário em um paciente de testes (normalemnte os bancos nos clientes da Iberwan possuem um paciente para propósito de testes).
Crie Tele-consulta para o Paciente de testes. As consultas serão criadas para o médico (usuário que logou no IW)

Em seguida acesse o calendário do Google Workspace do usuário <nome_cliente>@iwsoftware.com.br  
No Google Workspace, aplicação de Calendário da conta <nome_cliente>iwsoftware.com.br, deverá existir uma agenda para cada médico para o qual criou-se Tele-consultas.
E dentro da Agenda desses médicos, deverá existir um evento para cada Tele-consulta criada.  

Esses testes são fundamentais para garantir que o IW-Telemedicina-API foi instalada corretamente está funcionando bem.e o IwCare está cnseguindo acessá-la.  

**O IW-Telemedicine-API não pode ser considerado *Instalado* se esses testes não forem bem sucedidos.** 


Aqui termina a etapa 4 da instalação do Iw-Telemedicina-API. Que é a etapa final da instalação.  

**IMPORTANTE:**  
>*Agora o diretório temporário de instalação pode ser excluído.  
Nele estão fontes e outros arquivos protegidos por direitos autorais.*  

---
**FIM.**


