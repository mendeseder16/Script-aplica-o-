# Script-aplica-o-

Posso gerar todo o código necessário (back-end Spring Boot, configuração de segurança, entidades, repositórios, serviços, controladores, testes, scripts de CI e instruções de deploy no Heroku). Antes de gerar o projeto completo, preciso confirmar alguns detalhes para ajustar o código ao seu ambiente e preferências. Responda por favor:

1. Linguagem/versão e build tool:
   - (recomendado Java 17 ou 21)
   - Maven ou Gradle

2. Estrutura do projeto:
   - Nome do pacote base (ex.: com.exemplo.estacionamento)?
   - Nome do artefato (ex.: estacionamento-api) e GroupId/ArtifactId?

3. Modelos de dados (se quiser algo além do básico abaixo, diga):
   - Proposta mínima que vou usar:
     - Veiculo (id, placa, modelo, cor, tipo (CARRO/MOTO), dataHoraEntrada, dataHoraSaida, valorCobrado)
     - Movimentacao ou Estadia (mesma coisa que Veiculo acima ou separada) — prefiro ter uma entidade Estadia separada e um cadastro de Veículo opcional
     - Usuario (id, username, password, roles)
   - Deseja armazenamento de histórico por veículo (várias estadias por veículo)? Sim/Não?

4. Regras de negócio / cobrança:
   - Como cobrar: hora cheia, minuto, fração (ex.: cobrar por hora ou por 15 minutos)? Ex.: R$ 5,00 por hora para carros, R$ 3,00 por hora para motos.
   - Tarifa inicial (ex.: primeira hora fixa), tarifas noturnas, tolerância (ex.: 15 minutos grátis)? Se não, eu implemento uma regra simples ajustável via application.properties.

5. Segurança:
   - Deseja autenticação baseada em JWT? Ou Basic Auth (HTTP Basic)? Recomendo JWT.
   - Haverá perfis: ADMIN e ATENDENTE por exemplo? Quais permissões cada perfil tem (ex.: somento ADMIN pode listar usuários, ATENDENTE pode registrar entrada/saída)?

6. Persistência:
   - Usará PostgreSQL (local) e Heroku (provisiona DATABASE_URL). Deseja usar Spring Data JPA com configurações para ambos ambientes e profiles (dev/prod)? Sim/Não?

7. Testes:
   - Deseja testes unitários com JUnit 5 + Mockito e testes de integração com Testcontainers (Postgres)? Posso incluir cobertura com Jacoco.
   - Deseja pipeline CI (ex.: GitHub Actions) para build, testes e cobertura?

8. Documentação/Outros:
   - Deseja documentação da API com Springdoc OpenAPI / Swagger UI?
   - Deseja exemplos de requests (curl) e instruções completas de deploy no Heroku (incluindo Procfile, ajustes de configuração, variáveis de ambiente)?

Quando confirmar essas opções eu gerarei:
- Estrutura de projeto (pom.xml ou build.gradle)
- Código fonte Java (entidades, DTOs, repositórios, serviços, controladores, configuração de segurança JWT, exceptions, mappers)
- application.properties / application.yml (profiles dev/prod) com placeholders para variáveis sensíveis
- Scripts e arquivos para Heroku (Procfile, system.properties se necessário)
- Testes unitários e integração (Testcontainers)
- Configuração do Jacoco e GitHub Actions workflow para CI com cobertura
- README com instruções de execução local, testes e deploy no Heroku, e exemplos de uso (curl).
