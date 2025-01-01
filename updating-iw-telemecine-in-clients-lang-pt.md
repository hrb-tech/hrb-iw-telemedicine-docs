# Procedimento de atualização do IW-Telemedicine-API

Para atualizar o projeto IW-Telemedicine-API em qualquer cliente da Iberwan,  
a seguinte estratégia deve ser usada:   
> Instalar a nova versão como se fosse a primiera instalação e testá-la de ponta aponta para garantir que tudo está funcionando corretamente.
Mudar o parametro 151 de todos os bancos do cliente, apontando URL da nova vesão.
Fazer mais um teste final de funcionamento de criação de uma teleconsulta. Idealmente na base de treinamento e usando paciente de teste.
Após teste final com sucesso, deletar a versão antiga imediatamente. A existencia de duas ou mais versões da telemedicina pode criar confusões dificeis de serem diagnósticadas prejudicando o Cliente em questão.


A seguir temos todos os passos para fazer a atualização do IW-Telemedine-API:  


1. Executar o mesmo procedimento de instalação inicial [Installation procedure](installing-iw-telemedicine-in-clients-lang-pt.md)
É importante observar que por **padrão** toda versão da IW-Telemedicine-API a ser instalada no cliente precisa ter **obrigatoriamente** a identificação da versão no seu proprio nome. Conforme orientações presentes no próprio procedimento de instalação inicial.
O nome em si do projeto no GitHub fica como prefixo e acrescenta-se no final _<TAG da nova versão no git - branch main> 
  

2. Fazer testes de ponta a ponta da nova versão:
Criando, atualizando e deletando eventos de teleconsultas usando Iw-Care configurado para acessar a nova versão.
Lembre-se de verificar no Calendário do usuário correto a respectiva criação de agendas com respectivos eventos de tele-consultas.   

3. Se todos os testes passarem com sucesso, atualizar na tela 151 a nova URL da IW-Telemedicne-API em todos os bancos do cliente;

4. Deletar completamente a versão antiga.
**Todas as referencias para o projeto antigo devem ser removidas.
ATENÇÃO: no Google Workspace, quando deletamos um projeto de Action Script, ele vai para a pasta de lixo.
Ele precisa ser deletado também da pasta de lixo.
Agindo desse modo serão evitados muitos possíveis conflitos com a nova versão, deixando o ambiente limpo.
A presença de mais um Script com os mesmos objetivos podem causar problemas do tipo:
* erros humanos. Dupla publicação do IW-Telemedicine-API.
* problemas de manutenção e segurança. Acesso acidental a versão incorreta.
* além de outros.  


