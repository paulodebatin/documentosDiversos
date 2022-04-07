#Boas práticas Api Rest

- Uso correto dos verbos HTTP;
- Rodar sobre https;
- Tratamento de CORS;
- Controle de segurança - Autenticação (Bearer, Oauth2) ou jogar sobre uma API Gateway (AWS, Kong);
- Validação de dados de entrada (Bean Validator);
- Registro de todos as requisições (dados de entrada, dados de saída, tempo de processamento);
- Crie uma estratégia de versionamento na API
- Controle de timeout (API Gateway) 
- Retries (API Gateway) 
- Limite de acesso por tempo (API Gateway)
- Tratamento de erro genérico;
- Não expor todos os dados. Devolva apenas os dados necessários (cuidado com os list, trate paginação). Não exponha a classe de modelo. 
Não devolva campos nulos. Use compreensão.
- Documentação (OpenApi/Swagger);
- Faça testes automatizados (https://cursos.alura.com.br/course/spring-boot-profiles-testes-deploy/task/81030). 
Procure usar um banco de dados em memoria (H2) ou então mockear a Respository.
- Externize senhas de acesso em variáveis de ambiente (https://cursos.alura.com.br/course/spring-boot-profiles-testes-deploy/task/81033)
- Evite tentativas de autenticação com força bruta: https://www.baeldung.com/spring-security-block-brute-force-authentication-attempts
Máximo de tentativas mal sucessedidas por ip. Senão bloqueio o ip por x horas;
- Evitar ataques DDoS e CSRF
- Boas práticas de segurança: https://snyk.io/blog/spring-boot-security-best-practices/
- Use o Ngix antes para redirecionar para o seu api: https://medium.com/@josevieiraneto/nginx-e-spring-boot-ecfb9575433e

- Rodando em um container (Docker) e sendo orchestrador para que em caso de caida levante outro e seja balanceado (Kubernetes)
- Monitore as API's (Spring Boot Actuator e Spring Boot Admin)
- Cache (lado client e server)
- Tratar multitenanty
- Para melhor a produtividade no desenvolvimento, trabalhe como profile (application-dev.properties, application-prod.properties, ...). 
Ex.:https://cursos.alura.com.br/course/spring-boot-profiles-testes-deploy/task/81026
	https://cursos.alura.com.br/course/spring-boot-profiles-testes-deploy/task/81033



- Automatize o deploy (https://cursos.alura.com.br/course/jenkins-integracao-continua/task/87079)

Exemplo de multiplos bancos: 
- https://medium.com/@joeclever/using-multiple-datasources-with-spring-boot-and-spring-data-6430b00c02e7
- https://www.youtube.com/watch?v=o2dGEBj2750


- Aplique teste de strees:
https://www.youtube.com/watch?v=j19OFRb8lLI
https://www.youtube.com/watch?v=Wjig_fVSL6w