# Aula 2 — Anatomia de um Prompt Eficaz

## O que você vai entender nesta aula

Todo prompt que funciona bem tem cinco componentes. Você vai aprender o que é cada um, por que cada um importa, o que acontece quando falta um deles, e como montar prompts eficazes a partir dessa estrutura — com exemplos reais que você pode usar agora.

---

## Por que a maioria dos prompts falha

Observe o que as pessoas pedem para a IA quando começam:

- "Escreva um texto sobre minha empresa."
- "Faça um e-mail profissional."
- "Me ajuda com marketing."
- "Cria um script de vendas."

Esses pedidos têm algo em comum: são vagos. O modelo vai gerar algo — sempre gera — mas vai ser genérico, porque o prompt não deu informação suficiente para gerar algo específico.

A diferença entre um prompt que funciona e um que não funciona não é a complexidade da tarefa. É a qualidade da instrução.

Pense assim: se você contratar um redator e dizer apenas "escreva um texto sobre minha empresa", o que ele vai perguntar antes de começar? Vai perguntar sobre o público, o tom, o objetivo, o produto, o contexto. Um bom prompt faz esse trabalho antes — fornece as informações que o "redator IA" precisaria perguntar.

---

## Os cinco componentes de um prompt eficaz

Toda instrução que funciona bem com IA tem cinco dimensões. Você não precisa usar todas as cinco em todo prompt — mas precisa saber quando cada uma faz diferença.

### Componente 1: Tarefa

A tarefa é o que você quer que a IA faça. Parece óbvio, mas a maioria das pessoas a descreve de forma vaga.

Uma tarefa clara especifica:
- O verbo de ação (escreva, analise, resuma, liste, crie, reformule, explique, revise)
- O tipo de output (e-mail, tópicos, parágrafo, script, lista, tabela)
- O que está sendo trabalhado

Compare:

**Fraco:** "Me ajuda com o e-mail"

**Forte:** "Escreva um e-mail de 5 parágrafos para um cliente que não respondeu meu orçamento há 10 dias"

A versão forte especifica o que fazer (escreva), o tipo de output (e-mail de 5 parágrafos), e a situação específica (cliente sem resposta, 10 dias).

### Componente 2: Contexto

O contexto é a informação de fundo que o modelo precisa para gerar algo relevante para você — não algo genérico.

Sem contexto, o modelo faz suposições. Com contexto, ele gera algo que se encaixa na sua situação.

O contexto pode incluir:
- Quem você é (profissão, tipo de negócio)
- Para quem é o output (cliente, colega, público em geral)
- Qual é a situação (cliente novo, cliente insatisfeito, lead frio)
- O que já aconteceu antes
- O que você quer evitar ou incluir

Compare:

**Sem contexto:** "Escreva uma proposta para um cliente."

**Com contexto:** "Escreva uma proposta para um cliente do ramo de estética em Belo Horizonte que pediu informações sobre gerenciamento de redes sociais. Ela é dona de clínica, 40 anos, nunca trabalhou com marketing digital. O orçamento dela é de R$1.500 por mês."

O segundo exemplo vai gerar algo que o cliente vai reconhecer como escrito para ela — não um template genérico.

### Componente 3: Restrições

Restrições são os limites e requisitos que a saída precisa respeitar. Elas direcionam o modelo dentro do espaço de possibilidades.

Restrições comuns:
- **Tamanho:** "em até 150 palavras", "em 3 parágrafos", "em uma frase"
- **Tom:** "formal", "descontraído", "direto", "acolhedor"
- **Formato:** "em tópicos", "com subtítulos", "em formato de tabela"
- **O que não incluir:** "sem jargão técnico", "sem emojis", "sem frases genéricas"
- **Restrições técnicas:** "sem mencionar concorrentes", "sem fazer promessas de resultado"

Restrições evitam que o modelo produza algo tecnicamente correto mas inutilizável para a sua situação.

Exemplo com restrições:

"Escreva um post para Instagram sobre benefícios de contratar um contador. Tom descontraído, máximo 80 palavras, sem termos técnicos, com uma pergunta no final para gerar comentários. Não inclua emojis."

### Componente 4: Exemplos

Exemplos são amostras de input e output que mostram ao modelo o padrão exato que você quer. São poderosos porque eliminam ambiguidade — mostram, não apenas descrevem.

Você pode usar exemplos de duas formas:

**Forma 1 — Mostrar o que você quer:**
"Escreva um título no estilo de: 'Você está perdendo dinheiro sem saber — e a solução é simples'. Quero o mesmo padrão, mas sobre gestão de tempo para autônomos."

**Forma 2 — Mostrar antes e depois:**
"Transforme esse texto de formal para informal. Exemplo: 'Informamos que o prazo foi prorrogado.' → 'A boa notícia: temos mais tempo!'. Agora faça o mesmo com: 'Comunicamos a suspensão temporária do serviço.'"

Exemplos funcionam especialmente bem quando você tem um tom, estilo ou formato específico que é difícil de descrever em palavras — é mais fácil mostrar.

### Componente 5: Formato do output

Formato do output especifica como você quer receber a resposta — não apenas o que a resposta deve conter.

Exemplos de especificação de formato:
- "Responda em formato de lista numerada"
- "Organize em seções com subtítulos"
- "Apresente em formato de tabela com colunas: Problema | Causa | Solução"
- "Responda com dois textos: um formal e um informal, para eu comparar"
- "Comece com a conclusão e depois explique o raciocínio"

Quando você não especifica o formato, o modelo escolhe — e nem sempre é o mais útil para o que você precisa. Especificar formato poupa tempo de reformatação posterior.

---

## Montando os cinco componentes: exemplos completos

Veja como a adição de cada componente transforma um prompt:

**Prompt nível 1 — Só tarefa:**
"Escreva um e-mail de cobrança."

**Prompt nível 2 — Tarefa + contexto:**
"Escreva um e-mail de cobrança para um cliente que está 15 dias atrasado no pagamento de uma consultoria de R$2.000. A relação é boa, mas ele não respondeu ao primeiro aviso."

**Prompt nível 3 — Tarefa + contexto + restrições:**
"Escreva um e-mail de cobrança para um cliente que está 15 dias atrasado no pagamento de uma consultoria de R$2.000. A relação é boa, mas ele não respondeu ao primeiro aviso. Tom cordial mas firme, máximo 150 palavras, sem ameaças ou linguagem jurídica, inclua opção de parcelamento."

**Prompt nível 4 — Todos os componentes:**
"Escreva um e-mail de cobrança para um cliente que está 15 dias atrasado no pagamento de uma consultoria de R$2.000. A relação é boa, mas ele não respondeu ao primeiro aviso.

Tom: cordial mas firme.
Tamanho: máximo 150 palavras.
Restrições: sem ameaças ou linguagem jurídica; inclua opção de parcelamento em 2x.
Formato: assunto do e-mail primeiro, depois o corpo do e-mail."

O quarto prompt vai gerar um resultado que você pode usar quase sem editar. Os primeiros três vão exigir revisão substancial.

---

## A diferença entre clareza e detalhamento excessivo

Existe um ponto de equilíbrio. Clareza é boa. Detalhamento excessivo pode ser contraproducente.

Quando um prompt tem informações demais — especialmente informações irrelevantes — o modelo pode se perder, fazer suposições para preencher lacunas, ou gerar algo que tenta satisfazer requisitos contraditórios.

Uma regra prática: inclua cada informação porque ela afeta o output que você quer. Se uma informação não afeta o resultado, não inclua.

Exemplo de detalhamento desnecessário:

"Escreva um post sobre o nosso produto X. A empresa foi fundada em 2018 pelo nosso CEO João Silva que tem 15 anos de experiência e o produto foi lançado em 2021 depois de dois anos de desenvolvimento pela nossa equipe de 12 pessoas que trabalha em São Paulo no Faria Lima e já atendemos mais de 300 clientes..."

Esse excesso de contexto irrelevante não vai melhorar o post — vai diluir o foco do modelo.

Contexto relevante: o que o produto faz, para quem, qual a principal dor que resolve, qual o tom da marca.

---

## Lendo o output para entender o que faltou no prompt

Um dos melhores exercícios é observar onde o resultado falhou e diagnosticar qual componente estava ausente.

| Se o resultado foi... | Provavelmente faltou... |
|----------------------|------------------------|
| Genérico, sem personalidade | Contexto (quem você é, para quem é) |
| Longo demais ou curto demais | Restrição de tamanho |
| Tom errado (muito formal / muito informal) | Restrição de tom |
| Formato diferente do que precisava | Especificação de formato de output |
| Não fez o que você pediu | Clareza na descrição da tarefa |
| Estilo diferente do que queria | Exemplo do estilo desejado |

Essa leitura diagnóstica é o coração da iteração — o assunto da Aula 5.

---

## O framework PCTEF na prática

Uma forma de memorizar os cinco componentes: **PCTEF** (Pedido, Contexto, Travas, Exemplos, Formato).

Você não precisa usar os cinco sempre. Use como checklist:

- **P** (Pedido/Tarefa): O que exatamente você quer que a IA faça?
- **C** (Contexto): Quem, para quem, qual situação, o que já aconteceu?
- **T** (Travas/Restrições): O que deve ou não deve ter? Tamanho, tom, restrições?
- **E** (Exemplos): Tem alguma amostra do que você quer?
- **F** (Formato): Como você quer receber o resultado?

Para um pedido simples — um resumo de texto, a tradução de um parágrafo — você provavelmente precisa de P e F. Para um e-mail importante, uma proposta, um script de vendas, você quer todos os cinco.

---

## Prompts de sistema vs. prompts de usuário

Há dois tipos de instrução que vale conhecer:

**Prompt de usuário** é o que você digita a cada conversa — a instrução normal que você dá.

**Prompt de sistema** (ou "instrução de sistema") é uma instrução permanente que define o papel, o estilo e as regras que o modelo deve seguir em toda a conversa. Alguns modelos permitem configurar isso; outros têm campos específicos para isso.

Por exemplo, você pode configurar um prompt de sistema como:

"Você é um assistente de marketing especializado em pequenas empresas brasileiras. Sempre que escrever textos, use linguagem clara, evite jargão técnico e inclua sempre uma chamada para ação. Quando eu pedir um texto, pergunte antes: para qual público e qual é o objetivo principal."

Com esse prompt de sistema ativo, cada pedido que você fizer já vem com esse contexto pré-carregado. É como ter um assistente que já conhece seu negócio — sem precisar reexplicar tudo toda vez.

O banco de prompts da Aula 7 vai mostrar como usar prompts de sistema de forma sistemática.

---

## Erros comuns

**Erro 1: Prompt muito curto por preguiça**
"Cria um texto de marketing" não é um prompt, é um desejo. Três minutos escrevendo um prompt bem estruturado economiza 20 minutos de revisão. A matemática é simples.

**Erro 2: Contexto irrelevante em vez de contexto útil**
Informação que não afeta o output não é contexto útil — é ruído. A história da empresa, o nome do fundador, o ano de criação raramente afetam a qualidade de um e-mail de follow-up.

**Erro 3: Esquecer o formato do output**
Pedir um texto e receber 12 parágrafos quando você precisava de 3 tópicos é resultado de não especificar o formato. O modelo não adivinha — ele assume.

**Erro 4: Restrições contraditórias**
"Seja criativo, mas siga exatamente este modelo" ou "Seja breve, mas cubra todos esses 15 pontos" cria conflito. O modelo vai tentar conciliar e vai produzir algo mediano que não satisfaz nenhum dos dois requisitos.

**Erro 5: Não testar variações**
Se um prompt gerou algo bom, tente variações. Adicione ou remova um componente e veja o que muda. Essa experimentação é onde você desenvolve intuição rápida.

---

## Exercício prático

Escolha uma tarefa que você faça repetidamente no seu trabalho ou negócio. Pode ser:

- Responder e-mails de clientes
- Criar posts para redes sociais
- Escrever propostas comerciais
- Resumir reuniões ou documentos

Escreva três versões do prompt para essa tarefa:

**Versão 1 — Como você escreveria naturalmente** (provavelmente vaga)

**Versão 2 — Adicionando contexto e restrições** (mais específico)

**Versão 3 — Usando todos os cinco componentes** (completo)

Execute as três versões no mesmo modelo. Compare os resultados. Anote o que mudou entre a versão 1 e a versão 3 — essa diferença é o valor que um bom prompt entrega.

Guarde a versão 3 — ela já é um candidato para o seu banco de prompts.

---

## Resumo

- Todo prompt eficaz tem cinco componentes: Tarefa, Contexto, Restrições, Exemplos, Formato.
- Tarefa: o verbo de ação + tipo de output + o que está sendo trabalhado.
- Contexto: quem você é, para quem é o output, qual é a situação específica.
- Restrições: tamanho, tom, formato, o que incluir ou excluir.
- Exemplos: amostras concretas do estilo ou padrão que você quer.
- Formato de output: como você quer receber o resultado.
- Clareza é mais importante que comprimento — inclua cada informação porque ela muda o resultado.
- Quando um resultado falha, diagnostique qual componente estava ausente — é sempre um deles.
- Prompts de sistema pré-carregam contexto permanente, eliminando repetição entre sessões.
