# Mapeamento de Rotas, Funções e Consultas
| Módulo | Rotas | Função/consulta no banco |
|---|---|---|
| Setores e perguntas | GET /api/setores, /api/setores/:slug/perguntas | leitura de setores, perguntas, opções |
| Avaliação | POST /api/avaliacoes | `enviar_avaliacao` |
| Manifestação | POST /api/manifestacoes; POST /api/acompanhar | `enviar_manifestacao`; `consultar_manifestacao` |
| Login | POST /api/login | `autenticar` |
| Dashboard | GET /api/admin/indicadores | `indicadores` + visões por setor, dia e turno |
| Gestão | GET/POST /api/admin/manifestacoes... | leitura + `movimentar_manifestacao` |
| Catálogo | POST/PATCH /api/admin/perguntas | inserção/atualização com RLS |
| Usuários | POST /api/admin/usuarios | `criar_usuario` (só Administrador) |
| TV Wall | GET /api/tv | `tv_wall_resumo` |
| Relatório | GET /api/admin/manifestacoes.csv | leitura sem o texto da manifestação |