# Segurança e Nuvem
- **Hospedagem:** em desenvolvimento, tudo roda localmente. Para publicar: frontend (Lovable/Vercel), backend Node.js (Render, Railway ou VPS) e PostgreSQL gerenciado ou em servidor próprio. Confirmar provedor, região e custo.
- **Conexão:** `DATABASE_URL` no `.env` do backend, com o usuário `fh_app`.
- **Perfis:** Administrador (tudo, usuários, auditoria); Ouvidoria (catálogo, manifestações, relatórios); Gestor de setor (leitura do próprio setor, sem notas internas).
- **Proteções:** RLS; funções com `search_path` fixo; senhas e códigos em bcrypt; bloqueio após 5 falhas; limite por IP; auditoria de movimentações; sem coleta de nome, CPF ou diagnóstico.
- **LGPD:** não prometer anonimato absoluto sem verificar logs do servidor e IPs. O texto livre pode conter dados pessoais; avisar o paciente na tela.
- **Pendências:** HTTPS na publicação; política de retenção e backup (`pg_dump`); trocar a senha inicial do administrador; revisar o rate limit atrás de proxy.