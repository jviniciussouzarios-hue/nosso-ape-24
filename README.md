# Nosso Apê 24 — mobile-first

Aplicativo React + Vite para planejar a vistoria, reforma, compras e mudança do apartamento de 24,64 m².

## Funcionalidades (v2)
- Painel: meta financeira, previsão, pagamentos, etapas e tarefas.
- Etapas: dez fases editáveis, com datas, responsáveis e conclusão.
- Tarefas: cadastro, ambiente, etapa, responsável, prazo e status.
- Vistoria: 14 verificações iniciais editáveis, ocorrências, conformidade e ressalvas.
- Orçamento: meta, poupança mensal, valores previstos, cotados e pagos, pagamentos avulsos.
- Compras: itens e serviços, ambiente, categoria, preço, loja, link e status.
- Fornecedores: cadastro, contato, orçamento e observações.
- Ambientes: medidas editáveis e desenho 2D/efeito 3D **apenas ilustrativo**.
- Galeria: imagens compactas e referências por link.
- Documentos: imagens/PDF pequenos armazenados localmente.
- Decisões: histórico editável por ambiente.
- Configurações: informações do apartamento, backup e restauração JSON.
- Navegação mobile com barra inferior, menu lateral e formulários em tela cheia.

## Limitações importantes
**Ainda não há Supabase configurado, login, sincronização entre dispositivos ou upload em nuvem.** Os registros ficam no `localStorage` do navegador. Arquivos de até 750 KB podem ser anexados, sujeitos à cota de armazenamento do navegador. Não use como repositório único de documentos importantes. A exportação de backup contém os dados e anexos, e deve ser guardada com segurança.

A planta/visualização 3D não está em escala nem corresponde a um modelo arquitetônico; depende das cotas oficiais e do projeto da arquiteta.

Valores iniciais são exemplos ilustrativos, não preços pesquisados. **Não duplique pagamentos**: o total pago soma campos pagos dos itens e pagamentos avulsos.

## Desenvolvimento
```bash
npm install
npm test
npm run dev
npm run build
```

## Vercel
Importe `jviniciussouzarios-hue/nosso-ape-24`, framework Vite, build `npm run build`, saída `dist`. O GitHub Actions executa testes e build em pushes para `main`.

## Próxima integração de produção
Criar um projeto Supabase independente, tabelas com RLS e políticas por membros do projeto, autenticação por e-mail, Storage privado para anexos, e sincronização entre usuários. Nunca expor chaves secretas no frontend. Esta integração exige projeto e configuração reais antes de poder ser validada.
