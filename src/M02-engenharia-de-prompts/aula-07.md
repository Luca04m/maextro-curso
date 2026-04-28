# Aula 7 — Construindo seu Banco de Prompts Pessoal

## O que você vai entender nesta aula

Um banco de prompts é o seu maior ativo de produtividade com IA. Esta aula ensina por que construir um, como estruturá-lo, o que salvar, o que descartar, e como usar para que cada semana seja mais eficiente do que a anterior.

---

## Por que um banco de prompts é um ativo

Imagine que você passou 20 minutos desenvolvendo o prompt perfeito para escrever propostas comerciais. Testou, refinou, chegou a uma estrutura que gera resultados excelentes.

Se você não salvou esse prompt, na próxima vez que precisar, vai reconstruir do zero — ou usar algo inferior.

O banco de prompts resolve o problema que o modelo não resolve: memória entre sessões. O modelo não lembra de você. O banco de prompts lembra.

Com o tempo, seu banco de prompts se torna:

- **Um sistema de produtividade:** tarefas que levavam 30 minutos levam 5
- **Um ativo de conhecimento:** representa meses de refinamento e aprendizado
- **Uma vantagem competitiva real:** seus prompts são calibrados para seu negócio, seu público, seu tom — não são genéricos

Um banco de prompts bem mantido por 6 meses tem mais valor para o seu negócio do que qualquer ferramenta de IA que você vai pagar.

---

## O que salvar (e o que descartar)

Nem todo prompt precisa ir para o banco. Salvar indiscriminadamente cria um arquivo cheio de lixo que é difícil de usar.

**Salve quando:**
- O prompt gerou um resultado que você usou com mínima edição
- É uma tarefa que você vai repetir — semanal, mensal ou em projetos futuros
- O prompt levou mais de 3 iterações para funcionar (porque o trabalho de refinamento tem valor)
- É uma estrutura geral adaptável para várias situações

**Descarte (ou não salve) quando:**
- Foi para uma situação única que não vai se repetir
- O resultado precisou de edição substancial (o prompt precisa de mais refinamento antes de ser salvo)
- Existe uma versão melhor do mesmo tipo no banco

---

## A estrutura de um prompt bem documentado

Um prompt salvo precisa de mais do que o texto do prompt. Sem contexto, você não sabe quando usar, como adaptar, ou o que esperar.

**Template de prompt documentado:**

```
NOME DO PROMPT:
[Nome descritivo e específico — ex: "Follow-up de proposta sem resposta (WhatsApp)"]

CATEGORIA:
[Vendas / Conteúdo / Operação / Comunicação com clientes / Análise]

QUANDO USAR:
[Descrição de 1-2 linhas de quando aplicar este prompt]

PRÉ-REQUISITOS:
[O que você precisa ter antes de usar — ex: "ter enviado a proposta há pelo menos 5 dias"]

PROMPT:
[O texto completo do prompt, com [VARIÁVEIS] em maiúsculo onde você vai personalizar]

RESULTADO ESPERADO:
[O que o prompt gera — ex: "Mensagem de WhatsApp de 80-100 palavras para follow-up"]

NOTAS:
[Observações de uso — o que funcionou, o que não funcionou, como adaptar]

ATUALIZADO EM:
[Data da última revisão]
```

Esse nível de documentação parece excessivo no início. Com 30+ prompts no banco, é o que diferencia um banco utilizável de um arquivo caótico.

---

## Estrutura por categorias

Organize seu banco em categorias que refletem as áreas do seu negócio. Uma organização sugerida:

**Categoria 1 — Vendas e Prospecção**
- Scripts de abordagem inicial
- Respostas a objeções (por tipo de objeção)
- Follow-up após proposta
- Scripts de discovery call
- Proposta comercial (por seção)

**Categoria 2 — Comunicação com Clientes**
- Onboarding (primeiro e-mail após contratação)
- Atualizações de projeto
- Respostas a reclamações
- Feedback e pesquisa de satisfação
- Cobrança (por estágio: aviso, vencido, muito atrasado)

**Categoria 3 — Conteúdo**
- Post educativo Instagram
- Post de prova social
- Carrossel
- Roteiro de vídeo curto
- Calendário editorial
- Newsletter
- Stories de bastidor

**Categoria 4 — Análise e Estratégia**
- Análise de métricas mensais
- Diagnóstico de processo
- Análise competitiva
- Feedback de clientes
- Brainstorming de ideias

**Categoria 5 — Operação**
- SOPs (procedimentos)
- Contratação (descrição de vaga, roteiro de entrevista)
- Planilhas e relatórios
- Resumo de reunião

**Categoria 6 — Prompts de Sistema**
- Contexto permanente do negócio
- Tom de voz e identidade de marca
- Persona do cliente ideal

---

## O prompt de contexto: o mais importante do banco

O prompt de contexto é um tipo especial de prompt que você usa para "apresentar" seu negócio ao modelo no início de cada sessão.

Ele substitui o problema da ausência de memória: em vez de esperar que o modelo lembre quem você é, você informa no começo de cada sessão relevante.

**Template de prompt de contexto:**

```
CONTEXTO DO MEU NEGÓCIO

Nome do negócio: [nome]
O que faço: [descrição clara do serviço/produto]
Público que atendo: [descrição detalhada do cliente ideal]
Problema que resolvo: [o que o cliente tem antes e depois de trabalhar comigo]
Meu diferencial: [o que me diferencia de outras opções]
Tom de comunicação da minha marca: [formal/descontraído/técnico/próximo — com exemplos]
O que minha marca jamais faria/diria: [restrições de posicionamento]
Canais que uso: [Instagram, WhatsApp, e-mail, etc.]

Ao trabalhar comigo nesta sessão, considere sempre este contexto ao gerar qualquer texto ou análise.
```

Quando você começa uma sessão de trabalho de conteúdo ou comunicação colando esse contexto, a qualidade dos resultados aumenta substancialmente — porque o modelo sabe quem você é desde o primeiro prompt.

---

## Como construir o banco progressivamente

O erro mais comum é tentar construir o banco completo antes de começar a usar. O resultado é um projeto que nunca sai do papel.

A abordagem certa é construir enquanto usa:

**Semana 1-2:** Use a IA normalmente. Quando encontrar um prompt que funcionou bem, documente.

**Semana 3-4:** Revise os prompts salvos. Algum pode ser melhorado? Alguma categoria está faltando?

**Mês 2 em diante:** Use o banco como ponto de partida para novas tarefas similares. Adapte e salve a versão adaptada.

Em 30 dias de uso consistente, você vai ter 15-20 prompts úteis. Em 90 dias, 50-60. Isso já é suficiente para cobrir 80% das suas tarefas recorrentes.

---

## Ferramentas para organizar o banco

Você não precisa de ferramenta sofisticada. O que importa é que seja acessível rapidamente quando você precisar.

**Opção 1 — Notion**
Banco de dados com tabela por prompt. Filtre por categoria, data, resultado esperado. É fácil de pesquisar e atualizar.

Estrutura sugerida no Notion:
- Tabela com colunas: Nome | Categoria | Quando usar | Data de criação | Avaliação (1-5)
- Cada linha abre uma página com o prompt completo documentado

**Opção 2 — Google Docs**
Um documento por categoria. Simples, sempre acessível, fácil de copiar e colar.

**Opção 3 — Arquivo de texto simples**
Para quem prefere velocidade. Um arquivo .txt ou .md por categoria, organizados em pastas. Sem banco de dados — só texto puro.

**Opção 4 — Pasta de Notas (Apple Notes, Google Keep)**
Para quem já usa esses apps no dia a dia. Menos poderoso para pesquisa, mas zero atrito para adicionar novos prompts.

A melhor ferramenta é a que você vai realmente usar — não a mais sofisticada.

---

## O ciclo de manutenção

Um banco de prompts não documentado fica desatualizado em meses. Modelos evoluem, seu negócio muda, você aprende coisas novas.

Estabeleça uma rotina simples de manutenção:

**Semanal (5 minutos):**
- Adicionar prompts que funcionaram bem esta semana
- Marcar prompts que não performaram para revisar

**Mensal (30 minutos):**
- Revisar prompts marcados para revisar
- Verificar se alguma categoria importante está faltando
- Atualizar o prompt de contexto do negócio se algo mudou

**Trimestral (1 hora):**
- Revisar prompts que não foram usados (valem manter?)
- Verificar se os melhores prompts ainda funcionam igual com o modelo atual
- Consolidar variantes do mesmo prompt em uma versão unificada melhor

---

## Compartilhando e colaborando

Se você trabalha com uma equipe, mesmo pequena, um banco de prompts compartilhado multiplica o valor:

- Todos usam os mesmos padrões de comunicação
- O tempo investido em refinar um prompt beneficia toda a equipe
- Novos integrantes têm acesso imediato ao conhecimento acumulado

Para equipes pequenas (2-5 pessoas), um documento compartilhado no Google Drive já funciona.

Para equipes maiores, Notion com permissões é mais adequado.

---

## Prompts de sistema: configurando a IA para o seu negócio

Alguns modelos permitem configurar "instruções permanentes" — texto que é incluído em toda conversa automaticamente, sem você precisar colar toda vez.

No ChatGPT, isso está em Configurações > Personalizar ChatGPT.
No Claude, algumas interfaces permitem configurar instruções do sistema.

O que colocar nas instruções permanentes:
- Quem você é e o que faz (em 3-5 linhas)
- Tom de comunicação preferido
- Formato de resposta preferido (direto ao ponto? com exemplos? em tópicos?)
- O que você não quer (posts de LinkedIn genéricos, frases motivacionais, emojis excessivos)

Exemplo de instrução permanente:
```
Sou [nome], [o que faço] para [público]. Sempre que gerar textos para mim, use
linguagem [adjetivo] e [adjetivo]. Evite [o que não usar]. Quando gerar conteúdo
para redes sociais, priorize [tipo de abordagem]. Quando não tiver contexto
suficiente, pergunte antes de gerar.
```

---

## Erros comuns

**Erro 1: Salvar prompts que não foram refinados**
Um prompt que precisou de 10 iterações para funcionar tem valor — mas salve a versão final, não a versão inicial. Salvar prompts ruins polui o banco.

**Erro 2: Prompts sem contexto de uso**
"Prompt de e-mail" não diz quando usar, para quem, com que objetivo. Sem o contexto, você não sabe se aquele prompt resolve o seu problema atual.

**Erro 3: Banco sem organização**
Depois de 30 prompts em uma lista sem estrutura, encontrar o que você precisa fica mais difícil do que construir do zero. Organize desde o início.

**Erro 4: Nunca revisar**
Prompts que eram bons seis meses atrás podem ser mediocres hoje — porque o modelo evoluiu, porque você aprendeu mais, porque seu negócio mudou. Revisão periódica mantém o banco útil.

**Erro 5: Não adaptar o prompt de contexto**
O contexto do seu negócio muda: novo serviço, novo público, novo posicionamento. Se o prompt de contexto não reflete isso, todos os resultados vão ser calibrados para quem você era — não para quem você é.

---

## Exercício prático

**Passo 1:** Escolha a ferramenta para o seu banco (Notion, Google Docs, arquivo de texto — o que for mais simples para você agora).

**Passo 2:** Crie as seis categorias sugeridas.

**Passo 3:** Escreva seu prompt de contexto do negócio. Use o template fornecido. Isso leva 15-20 minutos mas vai ser o prompt mais valioso do banco.

**Passo 4:** Revise as aulas anteriores e identifique os 5 prompts que você mais usou ou gostaria de ter usado. Documente cada um no formato completo.

**Passo 5:** Use o banco hoje. Abra uma conversa com IA, cole o prompt de contexto, e execute um dos prompts documentados. Observe a diferença de qualidade quando o modelo tem contexto pré-carregado.

---

## Resumo

- O banco de prompts substitui a memória que o modelo não tem — é o seu maior ativo de produtividade com IA.
- Salve prompts que você vai repetir, que levaram refinamento, e que geraram resultados utilizáveis.
- Um prompt bem documentado inclui: nome, categoria, quando usar, o prompt completo com variáveis marcadas, resultado esperado, notas.
- Organize por categorias: Vendas, Comunicação, Conteúdo, Análise, Operação, Prompts de Sistema.
- O prompt de contexto é o mais importante — carrega quem você é para cada sessão nova.
- Construa progressivamente: documente enquanto usa, não antes.
- Mantenha com ciclo semanal, mensal e trimestral.
- A melhor ferramenta é a que você vai realmente usar — não a mais sofisticada.
