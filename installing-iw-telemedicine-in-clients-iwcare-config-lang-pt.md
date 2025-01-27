# Instalação IW-Telemedicina-API - Etapa 4:  
## Configuração final e testes de integração

>Essa etapa usa o Aplicatico Iw-Care e o Navegador 

1. **Acessar o IW-Care:**

> Escolha um banco qualquer do cliente para fazer as configurações e testes presentes nessa etapa.
> *Prefernciacialmente* use um banco de treinamento ou de homologação.

Fazer Login no IW-Care com o usuário administrador e que a nivel de IW seja considerado um médico com acesso ao prontuário.


3. **Acessar a tela 151:**  

4. **Procurar a propriedade: GLB_TELEMEDICINE_URL**  
Caso já exista, altere o valor da propriedade para o valor da URL BASE do IW-Telemedicina-API, gerada na etapa anterior - passo 1.  
Caso essa propriedade ainda não exista no IW, adicione a propriedade e valore a mesma adequadamente.    
E Salve as propriedades.

7. **Fazer vários testes de video-chamandas
Acessar as telas do IW-Care que permitem criar e acessar Teleconsultas.  
A medida que novas versões do IW-Care são disponibizadas, novas telas serão criadas para acesso da telemedicina.
Hoje apenas as telas de Evoluções clínicas do Prontuário já oferecem esse acesso.

Simule a criação de varias teleconsultas bem como a realização das mesmas.
Caso não saiba como usar as funcionalidades de teleconsultas no IWCare, consulte o manual do IWCare.  

Posicione o Prontuário em um paciente de testes (normalmente os bancos nos clientes da Iberwan possuem um paciente para propósito de testes).
Crie Tele-consulta para o Paciente de testes. As consultas serão criadas para o médico (usuário que logou no IW-Care)

Em seguida acesse o calendário do Google Workspace do usuário <nome_cliente>@iwsoftware.com.br  
Na aplicação de Calendário da conta <nome_cliente>iwsoftware.com.br, deverá existir uma agenda para cada médico para o qual criou-se Tele-consultas.
E dentro da Agenda desses médicos, deverá existir um evento para cada Tele-consulta criada.  

Esses testes são fundamentais para garantir que o IW-Telemedicina-API foi instalada corretamente,  está funcionando bem e está conseguindo acessá-la.  

**O IW-Telemedicine-API não pode ser considerado *Instalado* se esses testes não forem bem sucedidos.**  
Os testes realizados anteriomente (até a Etapa 3) são importantes também, pois se eles falharem os testes dessa Etapa 4 irão falhar também.
O testes anteriores certificam que a instalação está evoluindo corretamente e que as possibilidades dos testes da Etapa 4 passarem também são muito altas.  


Aqui termina a etapa 4 da instalação do Iw-Telemedicina-API. Que é a etapa final da instalação.  

8. **Configurar o parâmetro GLB_TELEMEDICINE_URL nos demais bancos de dados.
> A telemedicina só irá funcionar nops bancos de dados que tiverem o parametro GLB_TELEMEDICINE_URL valorado corretamente. 

> **IMPORTANTE:**  
> *Agora o diretório temporário de instalação pode ser excluído.  
 

**FIM.**


