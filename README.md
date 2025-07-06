# Projeto EJB Demo com WildFly

Este projeto é um exemplo simples de aplicação EJB com um Servlet usando Jakarta EE (EJB + Servlet), empacotado como um WAR e executado no servidor WildFly.

---

## Requisitos

- Java JDK 21 instalado e configurado no sistema (variável `JAVA_HOME`)
- Maven instalado
- Servidor WildFly 30.0.0.Final baixado e descompactado

---

## Como compilar e gerar o WAR

1. Abra o terminal na pasta raiz do projeto (onde está o arquivo `pom.xml`).
2. Execute o comando para limpar, compilar o projeto e gerar o arquivo `.war`:

   ```bash
   mvn clean package
   
3. Após o processo, o arquivo ejb-demo-1.0-SNAPSHOT.war será criado na pasta target/

## Como executar o servidor WildFly

1. Abra o terminal na pasta do WildFly, exemplo:

	cd /caminho/para/wildfly-30.0.0.Final/bin

2. Execute o WildFly com o script:

	./standalone.sh

3. Aguarde até que o WildFly inicie completamente.	

## Como fazer o deploy da aplicação

1. Copie o arquivo WAR gerado para a pasta de deploy do WildFly:

	cp /caminho/do/projeto/target/ejb-demo-1.0-SNAPSHOT.war /caminho/para/wildfly-30.0.0.Final/standalone/deployments/
	
2. O WildFly fará o deploy automaticamente.
3. Verifique no terminal do WildFly se a aplicação foi implantada sem erros.

## Como acessar o servlet

1. Abra o navegador e acesse a URL:

	http://localhost:8080/ejb-demo-1.0-SNAPSHOT/hello
	
2. Você verá a mensagem:

	Olá usuario, este é um EJB!
	
## Arquivos importantes do projeto

1. pom.xml - configurações Maven e dependências
2. src/main/java/com/ejb/HelloBean.java - Bean EJB com a lógica
3. src/main/java/com/ejb/HelloServlet.java - Servlet que usa o EJB
4. src/main/webapp/WEB-INF/web.xml - configuração do servlet (opcional)

## Dicas

1. Use a URL com o nome do WAR para acessar.
2. Para parar o WildFly, pressione Ctrl+C no terminal.
3. Após alterações no código, rode mvn clean package e atualize o WAR em deployments.
4. WildFly roda na porta 8080 por padrão.









