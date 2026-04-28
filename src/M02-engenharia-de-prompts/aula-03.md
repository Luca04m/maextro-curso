# Aula 3 — Tipos de Prompts e Quando Usar Cada Um

## O que você vai entender nesta aula

Existe uma diferença fundamental entre pedir para a IA criar algo do zero, pedir para ela explicar algo que você tem dúvida, pedir para ela revisar um texto seu, ou pedir para ela transformar um formato em outro. Cada situação tem uma lógica própria e um tipo de prompt próprio. Esta aula cobre os seis tipos principais — com exemplos aplicáveis imediatamente.

---

## Por que tipos de prompts importam

Imagine que você precisa de ajuda com um texto e chega em um escritório com um redator, um revisor, um professor, um editor e um tradutor — todos profissionais, todos competentes, mas com funções bem diferentes.

Se você entrega seu rascunho ao redator esperando que ele revise, vai ficar frustrado — ele vai reescrever tudo do zero. Se você pede ao revisor que crie um texto novo, ele vai fazer o que pode mas não é para isso que ele é bom.

Com IA é igual. O modelo é capaz de fazer muita coisa — mas a instrução certa para cada situação gera um resultado muito melhor do que uma instrução genérica.

Os seis tipos principais são:

1. **Geração** — criar algo novo
2. **Transformação** — converter algo existente em outro formato
3. **Revisão/Melhoria** — aprimorar algo que já existe
4. **Explicação** — entender algo
5. **Análise** — extrair insights de um conteúdo
6. **Conversação/Raciocínio** — pensar junto com a IA

Cada um tem sua estrutura ideal.

---

## Tipo 1: Prompt de Geração

**O que é:** Você pede que a IA crie algo do zero — um texto, um script, um plano, uma lista, um e-mail.

**Quando usar:** Quando você está partindo do branco. Não tem rascunho, não tem base — você quer que a IA produza o primeiro draft.

**Estrutura ideal:**
- Tarefa + tipo de output claramente especificado
- Contexto rico (para quem, qual objetivo, qual situação)
- Restrições (tom, tamanho, o que incluir/excluir)
- Formato de output

**Exemplos:**

```
Crie um script de abordagem para WhatsApp para captar clientes de uma clínica
de estética. O objetivo é converter leads que viram o anúncio e mandaram mensagem
perguntando os preços. Tom: acolhedor e profissional. Máximo 120 palavras.
Inclua uma pergunta para engajar a resposta.
```

```
Escreva 5 títulos para um post sobre os erros mais comuns na gestão financeira
de MEIs. Cada título deve ser diferente em abordagem: um problema, uma solução,
uma provocação, uma curiosidade e um benefício.
```

```
Crie um roteiro de 7 e-mails de nutrição para leads que se cadastraram em um
e-book sobre gestão do tempo. Cada e-mail: assunto + 3 linhas descrevendo o conteúdo.
Objetivo: preparar para uma oferta de consultoria no e-mail 7.
```

**O que evitar em prompts de geração:**
- Não especificar o tipo de output (a IA vai escolher — pode não ser o que você quer)
- Contexto genérico ("para clientes") em vez de específico ("para donos de pet shop com 1 funcionário")
- Não definir o objetivo (o texto vai parecer lindo mas não vai servir para nada)

---

## Tipo 2: Prompt de Transformação

**O que é:** Você fornece algo que já existe e pede para a IA converter em outro formato, idioma, nível de complexidade ou tom.

**Quando usar:** Quando você tem material bruto que precisa virar outra coisa. Um relatório que precisa virar apresentação. Um texto formal que precisa ser mais informal. Uma lista que precisa virar parágrafos.

**Estrutura ideal:**
- Forneça o conteúdo original (cole o texto, a lista, os dados)
- Especifique o ponto de chegada claramente
- Indique o que manter e o que pode mudar

**Exemplos:**

```
Transforme este relatório financeiro em uma explicação simples para um cliente
sem conhecimento de finanças. Mantenha os números mas explique o que cada um
significa na prática. [COLE O RELATÓRIO AQUI]
```

```
Converta esta lista de tópicos de reunião em um e-mail de ata profissional.
Formato: data, participantes, decisões tomadas, próximos passos com responsáveis.
[COLE A LISTA DE TÓPICOS AQUI]
```

```
Reescreva este trecho do meu contrato em linguagem clara e acessível,
sem perder o significado jurídico. Mantenha os mesmos direitos e obrigações,
mas use frases curtas e vocabulário comum. [COLE O TRECHO AQUI]
```

```
Pegue este post de blog e transforme em:
a) Um post para Instagram (máximo 150 palavras + 3 hashtags)
b) Um thread de Twitter/X com 5 tweets
c) Um título e subtítulo para YouTube

[COLE O POST AQUI]
```

**O que evitar:**
- Não fornecer o material original (a IA vai inventar algo genérico)
- Não especificar o "ponto de chegada" (a IA transforma para o que achar melhor)
- Deixar ambíguo o que pode e o que não pode mudar

---

## Tipo 3: Prompt de Revisão e Melhoria

**O que é:** Você tem um texto, plano ou documento que você escreveu, e quer que a IA aprimore, corrija ou fortaleça.

**Quando usar:** Quando você tem um rascunho mas sabe que pode ser melhor. Quando quer um segundo olhar. Quando precisa corrigir algo específico (gramática, clareza, tom).

**Estrutura ideal:**
- Forneça o que você escreveu
- Especifique o que quer que melhore (clareza? tom? fluidez? argumentação?)
- Diga o que não pode mudar (estrutura, dados, partes específicas)
- Informe o objetivo do texto e o público

**Exemplos:**

```
Revise este e-mail para torná-lo mais persuasivo. Mantenha o conteúdo e o
tamanho aproximado, mas torne os argumentos mais convincentes e o CTA mais
claro. Público: gerente de compras de empresa de médio porte. [COLE O E-MAIL]
```

```
Melhore a clareza deste texto. Frases muito longas, substitua por frases curtas.
Jargão técnico de RH, traduza para linguagem comum. Mantenha as ideias.
[COLE O TEXTO]
```

```
Leia esta proposta comercial e me diga:
1. Quais são os 3 pontos mais fracos
2. O que está faltando
3. O que está excelente e não deve ser mudado
[COLE A PROPOSTA]
```

```
Corrija a gramática e pontuação deste texto sem alterar o estilo ou o vocabulário.
[COLE O TEXTO]
```

**A diferença entre revisão e geração:**

Revisão preserva sua voz e estrutura — a IA aprimora o que você fez. Geração cria do zero, com a voz padrão da IA.

Para materiais que vão comunicar sua marca, revise em vez de gerar. O resultado vai soar mais autêntico.

---

## Tipo 4: Prompt de Explicação

**O que é:** Você quer entender algo. Pode ser um conceito, um trecho de texto, um código, uma palavra técnica, um mecanismo.

**Quando usar:** Quando está estudando, quando encontrou algo que não entende, quando precisa explicar para outra pessoa e primeiro quer entender você mesmo.

**Estrutura ideal:**
- Informe o que você quer entender
- Especifique seu nível de conhecimento (iniciante? avançado? nunca ouvi falar?)
- Peça analogias ou exemplos se quiser
- Especifique o objetivo (aprender? explicar para cliente? decidir?)

**Exemplos:**

```
Explique o que é margem de contribuição como se eu tivesse 16 anos e nunca
tivesse estudado finanças. Use um exemplo com um produto simples tipo vender
salgado na escola.
```

```
Explique este parágrafo do meu contrato de prestação de serviço. O que ele
significa na prática? Se eu precisar cancelar o contrato antes do prazo, o que
acontece segundo este trecho? [COLE O PARÁGRAFO]
```

```
O que é funil de vendas? Me explique em 3 níveis:
1. A explicação em 1 frase para alguém que nunca ouviu o termo
2. A explicação em 3 parágrafos para alguém que quer entender como funciona
3. Quais são os 3 pontos onde a maioria dos pequenos negócios erra no funil
```

```
Explique a diferença entre tráfego pago e tráfego orgânico. Eu sei o básico
mas quero entender: quando vale mais a pena investir em cada um? Dê exemplos
de situações reais.
```

**O truque de "nível de explicação":**

Um dos recursos mais poderosos é especificar o nível de profundidade que você quer. Compare:

- "Explique SEO" → você vai receber uma explicação genérica de nível desconhecido
- "Explique SEO como se eu fosse dono de um salão de beleza que nunca fez marketing digital" → você recebe uma explicação calibrada para você

Quanto mais específico o seu nível e contexto, mais útil é a explicação.

---

## Tipo 5: Prompt de Análise

**O que é:** Você fornece dados, um texto, um conjunto de informações, e pede que a IA extraia padrões, tendências, insights, problemas ou oportunidades.

**Quando usar:** Quando você tem dados mas não sabe o que fazer com eles. Quando quer um diagnóstico. Quando precisa de uma avaliação externa de algo.

**Estrutura ideal:**
- Forneça o material a ser analisado
- Especifique o ângulo de análise (o que você quer descobrir?)
- Indique o que fazer com o resultado (decisão? apresentação? melhoria?)

**Exemplos:**

```
Analise estes resultados de atendimento ao cliente do último trimestre e identifique:
- Os 3 principais problemas recorrentes
- O que parece ser a causa raiz em cada caso
- Quais mudanças teriam maior impacto
[COLE OS DADOS OU RESUMO DOS ATENDIMENTOS]
```

```
Analise os títulos dos 10 posts que mais performaram na minha conta do Instagram
(em termos de curtidas e salvamentos) e identifique os padrões comuns. O que
eles têm em comum que pode explicar a performance?
[COLE OS TÍTULOS]
```

```
Leia minha bio do Instagram e me diga:
- O que comunica bem
- O que está confuso ou genérico
- O que está faltando para um visitante entender quem sou e por que me seguir
[COLE A BIO]
```

```
Compare estas duas propostas comerciais e diga qual é mais persuasiva e por quê.
Liste os pontos fortes de cada uma e qual eu deveria usar como base.
[COLE AS DUAS PROPOSTAS]
```

**Análise vs. Revisão:**

Revisão aprimora o que você tem. Análise extrai insights do que você tem. Em uma revisão, a IA reescreve. Em uma análise, a IA diagnostica.

---

## Tipo 6: Prompt de Conversação e Raciocínio

**O que é:** Você usa a IA como interlocutor para pensar em voz alta, testar ideias, explorar um problema, tomar uma decisão ou simular uma situação.

**Quando usar:** Quando você precisa pensar — não apenas produzir. Quando tem um problema sem solução clara. Quando quer antecipar objeções. Quando precisa de um "advogado do diabo".

**Estrutura ideal:**
- Apresente o problema ou a questão com contexto suficiente
- Defina o papel que você quer que a IA assuma (consultor? crítico? especialista?)
- Especifique o que você quer: apenas alternativas? uma recomendação? perguntas para você pensar?

**Exemplos:**

```
Estou pensando em lançar um curso online sobre organização financeira para MEIs.
Tenho 200 seguidores no Instagram, sem audiência prévia. Me faça 5 perguntas
difíceis que eu preciso responder antes de decidir se vale a pena.
```

```
Vou apresentar este plano de negócio para um investidor amanhã. Assuma o papel
de um investidor cético e experiente. Faça as 7 perguntas mais difíceis que
você faria sobre este plano. [COLE O PLANO]
```

```
Preciso decidir entre duas estratégias de precificação para meu serviço:
Opção A: R$500 por sessão avulsa
Opção B: R$1.500 por pacote de 4 sessões

Me ajude a pensar nas implicações de cada uma. Considere: fluxo de caixa,
percepção de valor, tipo de cliente que cada uma atrai, e a diferença no esforço
de vendas.
```

```
Quero melhorar o atendimento no meu negócio. Me faça 10 perguntas que me ajudem
a diagnosticar onde estão os gargalos, sem eu precisar descrever tudo antes.
```

**O poder do "assuma um papel":**

Quando você pede que a IA assuma um papel específico ("seja um investidor cético", "seja meu cliente mais exigente", "seja um especialista em marketing com 20 anos de experiência"), a qualidade e a relevância das respostas aumentam significativamente.

O modelo usa o papel como contexto para calibrar o tipo de resposta. Um "investidor cético" vai perguntar sobre ROI, riscos e evidências. Um "cliente insatisfeito" vai apontar problemas no serviço. Um "consultor de marketing experiente" vai falar sobre posicionamento e diferenciação.

---

## Misturando tipos: o prompt composto

Na prática, muitas situações exigem uma combinação de tipos. Você pode pedir análise + geração, ou revisão + transformação, em um único prompt estruturado.

**Exemplo de prompt composto (análise + geração):**

```
[ANÁLISE] Leia estas 3 avaliações de clientes do meu serviço e identifique:
- O principal elogio recorrente
- O principal problema recorrente

[GERAÇÃO] Com base na análise, escreva:
1. Um post para Instagram destacando o elogio como prova social (80 palavras)
2. Uma resposta padrão para o problema recorrente, que seja empática mas direta

Avaliações:
[COLE AS AVALIAÇÕES]
```

**Exemplo de prompt composto (transformação + revisão):**

```
Transforme esta lista de bullet points em um parágrafo fluido para usar em minha
apresentação. Depois, revise o parágrafo gerado para garantir que o tom é
executivo e a linguagem é precisa.

[COLE OS BULLET POINTS]
```

O prompt composto economiza tempo quando você tem etapas consecutivas claras. Mas cuidado: prompts muito longos com muitas instruções encadeadas podem gerar outputs confusos. Se tiver dúvida, quebre em dois prompts menores.

---

## Guia de referência: qual tipo usar quando

| Situação | Tipo de prompt |
|----------|---------------|
| Preciso criar um texto, e-mail, post do zero | Geração |
| Tenho um texto e quero em outro formato | Transformação |
| Escrevi algo e quero melhorar | Revisão |
| Não entendo um conceito ou documento | Explicação |
| Tenho dados ou textos e quero insights | Análise |
| Preciso pensar em um problema ou decisão | Conversação/Raciocínio |
| Tenho um rascunho e dados para trabalhar juntos | Composto |

---

## Erros comuns

**Erro 1: Usar geração quando precisava de revisão**
Você tem um texto com a sua voz e pede para a IA "melhorar". Ela reescreve tudo e você perde sua identidade no texto. Use revisão, não geração, quando quiser manter seu estilo.

**Erro 2: Usar análise sem fornecer o material**
"Analise minha estratégia de marketing" sem fornecer nenhum material específico gera análise genérica. A análise exige input concreto.

**Erro 3: Conversação sem um papel definido**
"O que você acha dessa ideia?" é vago. "Você é um empreendedor com 10 anos de experiência em e-commerce. O que você acha dessa ideia?" é focado.

**Erro 4: Pedir transformação sem especificar o destino**
"Transforme isso" sem dizer para o quê. Para Instagram? Para e-mail? Para texto formal? O modelo vai escolher — e não vai acertar o que você quer.

**Erro 5: Pedido composto mal estruturado**
Misturar muitas instruções sem separar claramente as etapas gera confusão. Se tiver 3 pedidos distintos, numere-os ou separe-os em seções claramente marcadas.

---

## Exercício prático

Escolha um projeto atual — qualquer coisa que você está trabalhando no seu negócio.

Escreva um prompt de cada tipo para esse projeto:
1. **Geração:** O que você precisaria criar do zero?
2. **Transformação:** Tem algum material que precisa virar outro formato?
3. **Revisão:** Tem algum texto que poderia ser melhorado?
4. **Análise:** Tem algum dado ou documento para analisar?
5. **Conversação:** Qual decisão você está adiando que poderia pensar junto com a IA?

Execute pelo menos dois desses prompts hoje e observe a diferença entre usar o tipo certo versus fazer um pedido genérico.

---

## Resumo

- Existem seis tipos principais de prompt: geração, transformação, revisão, explicação, análise e conversação.
- Cada tipo tem uma estrutura ideal e situações específicas onde funciona melhor.
- Geração parte do zero; transformação converte o que existe; revisão aprimora o que você escreveu.
- Análise extrai insights; explicação ensina; conversação ajuda a pensar e decidir.
- Especificar um papel ("seja um investidor cético") melhora significativamente prompts de conversação.
- Prompts compostos combinam tipos quando as etapas são claras e sequenciais.
- Usar o tipo errado gera o resultado errado — mesmo com um prompt bem estruturado.
