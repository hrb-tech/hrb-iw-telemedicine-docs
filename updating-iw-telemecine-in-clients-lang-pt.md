# Procedimento de atualização do IW-Telemedicine-API

Para atualizar o projeto IW-Telemedicine-API em qualquer cliente da Iberwan,  
recomendamos a seguinte estratégia:   
> Implantar o novo projeto e testar a nova versão para garantir que tudo está funcionando corretamente.
Depois de obter a nova URL onde os novos scripts irão responder as requisições HTTP,  
e configurar o IW-Care para operar com a nova URL, criando varias tele consultas usando as telas do IW-Care e simular todo o fluxo de tele-consultas.  

A seguir temos todos os passos para fazer a atualização do IW-Telemedine-API:  

*Step 1:* Faser uma cópia se segurança (backup) do Projeto no Google Drive do usário que instalou (Usuário do Google Work Spaces).
1. Acessar drive.google.com e fazer login com a conta do Google Work Space.
2. Localizar o projeto, usando pesquisar pelo nome do projeto.
3. Clicar com o botão direito no arquivo do projeto
4. Selecionar a opção "Fazer uma cópia"

Uma cópia do projeto é criada.
Esta cópia é independente do projeto original.  
A cópia não estárá vinculada ao projeto original de nenhuma forma.  
A cópia não estará Implantada (Deployed), mesmo que o projeto original esteja Implantado.  

**Importante Observar:  
A cópia de segurnça criada nessa etapa deve ser deletada do Google Drive depois dos testes da nova versão do IW-Telemedicine forem concluídos.**

*Step 2:* executar o mesmo procedimento de instalação inicial [Installation procedure](installing-iw-telemedicine-in-clients-lang-pt.md)
  

*Step 3:* Do tests creating, updating and deleting consult events using the Iw-Care cofigured to access the new deployment.
Remember to verify in the Calendar of target Google's Account all the actions executed in the tests. 

*Step 4:* Se todos os testes passarem com sucesso, remover comletamente  acopia feita no passo 1 em  2 lugares;
na pasta onde o projeto reside no Google Drive and também na paste de lixo.
**Todas as referencias para o projeto antigo devem ser removidas.
Mesmo que estejam na pasta de lixo do Google Drive**
Agindo desse modo serão evitados muitos possǘeis conflitos com a nova versão e deixa o ambiente limpo.
A presença de mais um Script com os mesmos objetivos podem causar problemas do tipo:
* erros humanos. Dupla publicação do IW-Telemedicine-API.
* prblemas de manutenção. Acesso aidental a versão incorreta.
* security problems. Accidental access to the wrong version.  
* além de outros.


