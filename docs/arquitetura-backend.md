# Arquitetura do Backend
**Decisão:** PostgreSQL (relacional, transacional, com controle de acesso por linha) + backend Node.js/Express. O banco é criado separadamente pelo terminal.

## Camadas
1. Frontend React: telas públicas e administrativas; só fala com a API.
2. Backend Express: valida entradas, aplica limite de requisições, autentica (JWT de 8 h) e chama funções do banco.
3. Banco: integridade (chaves, CHECK, UNIQUE), regras em funções, RLS e auditoria. O backend usa o usuário `fh_app`, sem privilégios de administrador do banco.

## Segurança
Consultas parametrizadas; RLS padrão-negar; código de acesso e senhas em bcrypt; bloqueio após 5 falhas em 15 min por protocolo; limite por IP no backend; CORS restrito; cabeçalhos com helmet; CSV protegido contra injeção de fórmulas.

## Escalabilidade
Índices por setor/data/status; agregações no banco; evolução multi-hospital com `hospital_id` em todas as tabelas e políticas.

## Limitações
Sem integração com escala de trabalho (turno/equipe "Não identificado") nem base de atendimentos (taxa de participação indisponível).