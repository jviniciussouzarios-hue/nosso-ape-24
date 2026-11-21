# Plano de implementação — Nosso Apê 24

## Objetivo e critérios de aceite
Aplicativo pessoal, mobile-first, para duas pessoas planejarem o apartamento de 24,64 m², desde vistoria até mudança. Cada módulo deve ter cadastro, edição, exclusão, busca, filtros, histórico de decisões e consistência financeira. Nenhuma funcionalidade é considerada concluída apenas por existir uma tela.

## Estado verificado (2026-11-21)
- React + Vite no GitHub; navegação mobile, etapas, tarefas, vistoria, orçamento, compras, fornecedores, ambientes, galeria, documentos e decisões.
- Orçamento por ambiente e prioridades, várias alternativas de compra por item, média, quantidade, frete, instalação e reserva.
- Persistência localStorage e backup JSON; anexos pequenos no navegador.
- CI configurada com teste Node e build Vite; **resultado remoto do build e teste visual não verificados**.
- Não há login, sincronização, storage remoto, auditoria multiusuário, planta fiel nem 3D real.

## Fase A — Qualidade, dados e UX mobile (em andamento)
1. Corrigir fluxos de valores, pagamentos, quantidades, alternativas e exclusões.
2. Testar rotas e estados vazios; compatibilidade com telas de 360–430 px; acessibilidade por teclado e toque.
3. Implementar migração versionada dos dados locais; validar importação/exportação e proteção contra perda de dados.
4. Automatizar testes unitários e smoke test de navegação em navegador; exigir build verde.

**Aceite:** criar/editar/excluir cada tipo de registro, recarregar sem perder dados, importar backup válido, e não duplicar preços de alternativas.

## Fase B — Banco e colaboração (pendente de infraestrutura)
1. Criar projeto Supabase **exclusivo** para o apartamento após confirmar organização/região/custo.
2. Supabase Auth (dois usuários), household, membership, papéis owner/editor.
3. Tabelas separadas por módulo, UUID, timestamps, versionamento e soft delete quando necessário.
4. Row Level Security para todas as tabelas expostas; permissões por household e storage privado.
5. Migrar dados do navegador com preview e prevenção de duplicidade; sincronização com tratamento de conflitos.
6. Configurar Vercel com VITE_SUPABASE_URL e chave **publishable**, nunca service_role no cliente.

**Aceite:** dois celulares autenticados visualizam as mesmas alterações; usuários externos não conseguem ler/escrever os dados.

## Fase C — Gestão de obra e custos
- Orçamento por ambiente/categoria/fase, prioridades, cenários essencial/importante/completo, reserva e saldo.
- Produtos com N links/alternativas, histórico de cotação manual, preço selecionado, quantidade, frete, instalação, status e prazo.
- Fornecedores, propostas, contratos, comprovantes, pagamentos parcelados e garantias.
- Vínculo pagamento↔item/serviço para impedir dupla contagem; datas de vencimento e projeção mensal.
- Agenda, dependências, responsáveis e lembretes opcionais.

**Aceite:** conciliação de compras, pagamentos e previsão, com totais reproduzíveis por cômodo e por prioridade.

## Fase D — Vistoria e arquitetura
- Checklist por cômodo, fotos, gravidade, status, protocolo e exportação de relatório PDF.
- Upload privado da planta da construtora e do projeto da arquiteta, com revisões e anotações.
- Medições por parede e posição de pontos elétricos/hidráulicos.
- Planta 2D calibrada; modelo 3D somente após planta e cotas verificadas.
- Regras técnicas: alvenaria estrutural não deve ser alterada sem projeto; lava-louças sobre lavadora somente com suporte independente e validação de fabricante/profissional.

**Aceite:** vistoria exportável e plantas vinculadas à versão correta; nenhuma dimensão ou intervenção estrutural inventada.

## Fase E — Validação e entrega
- CI verde, testes unitários/integrados/e2e mobile, revisão de RLS, storage e links.
- Testar em Android/iOS e largura de 360, 390 e 430 px, incluindo menu, teclado virtual e anexos.
- Deploy de preview, verificação do endereço público, revisão de erros e promoção a produção.
- Backup/restauração, documentação e checklist de recuperação.

## Regras
- Nenhum dado pessoal ou documento em repositório público.
- Não simular teste de browser ou sincronização não executados.
- Priorizar ferramentas gratuitas, sem reutilizar projetos Supabase de outros sistemas.
- Alterações pequenas, commits rastreáveis, sem apagar dados existentes.
