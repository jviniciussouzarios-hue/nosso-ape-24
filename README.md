# Nosso Apê 24

Aplicativo pessoal para planejar o apartamento de 24,64 m²: orçamento, compras, vistoria, fases, referências e medidas.

## Stack
React 18 + Vite 6 + Lucide React. Layout responsivo. Dados armazenados no localStorage e backup JSON.

## Executar
```bash
npm install
npm run dev
```

## Build e deploy Vercel
```bash
npm run build
```
Na Vercel, importe este repositório, escolha **Vite** e configure **Build Command** como `npm run build` e **Output Directory** como `dist`. Nenhuma variável de ambiente é necessária nesta versão.

## Importante
- Os valores iniciais são apenas exemplos, não cotações de mercado.
- A planta é **conceitual, sem escala** e não substitui a planta técnica da construtora ou arquiteta.
- O armazenamento é local por navegador; **não existe sincronização entre pessoas/dispositivos nem autenticação** nesta versão.
- Não publique documentos pessoais ou plantas detalhadas em um repositório público.
- O empilhamento de lava-louças sobre lavadora exige validação técnica e estrutura independente.

## Próximas entregas
1. Supabase Auth, RLS e projeto compartilhado entre dois usuários.
2. Banco para itens, cotações, fases, tarefas, vistoria e evidências.
3. Upload privado de planta, documentos, referências e projetos da arquiteta.
4. Comparação de fornecedores e histórico de preços.
5. Planta 2D/3D calibrada com medidas reais.

## Referências de produto
Houzz Projects (ideias, checklist e compras) e Planner 5D (planejamento 2D/3D, documentos e colaboração). Inspiração funcional, sem copiar identidade visual ou código proprietário.
