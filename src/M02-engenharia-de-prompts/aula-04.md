# Aula 4 — Fluxos de Trabalho com IA: Do Pedido à Entrega

## O que você vai entender nesta aula

Um único prompt raramente produz um entregável completo. A maioria dos projetos reais requer uma sequência de prompts — um fluxo. Esta aula ensina como estruturar esses fluxos: como decompor um projeto em etapas, como encadear prompts, como manter contexto entre eles, e como ir do pedido inicial até um resultado que você pode usar.

---

## A diferença entre um prompt e um fluxo

Um prompt resolve uma tarefa isolada. Um fluxo resolve um projeto.

Imagine que você precisa criar uma sequência de conteúdo para lançar um serviço novo no Instagram. Um único prompt não vai gerar isso bem — vai gerar algo genérico que não tem coerência de narrativa, não considera o público específico, e não progride de forma intencional.

Um fluxo faz isso em etapas:

1. Primeiro você define a estratégia (qual é o objetivo, quem é o público, qual é a narrativa)
2. Depois você gera o conteúdo etapa por etapa (post de problema, post de solução, post de prova, post de oferta)
3. Por fim você revisa e ajusta a coerência entre as partes

O fluxo transforma a IA de "gerador de conteúdo isolado" em "assistente de projeto".

---

## O princípio da decomposição

O primeiro passo para montar um fluxo é decompor o projeto em partes menores e independentes.

Decomposição funciona por um motivo técnico: o modelo trabalha melhor com instruções focadas do que com instruções gigantes. Quando você pede "escreva toda minha estratégia de marketing, o calendário de conteúdo do mês, os 20 posts e a bio do Instagram", vai receber algo raso sobre cada item. Quando você pede um item por vez, com o contexto do anterior, cada item vai ser mais profundo.

**Como decompor:**

1. Liste o produto final que você quer
2. Identifique as etapas lógicas para chegar lá
3. Identifique as dependências (etapa B depende da saída da etapa A?)
4. Execute na ordem certa, carregando o contexto relevante entre as etapas

**Exemplo:** Criação de uma proposta comercial

Produto final: proposta comercial completa para um cliente específico

Etapas:
1. Análise do cliente (quem é, qual é o problema, o que foi discutido)
2. Estrutura da proposta (quais seções incluir)
3. Geração de cada seção (apresentação, diagnóstico, solução, investimento, próximos passos)
4. Revisão de coerência e persuasão
5. Ajuste de tom e formatação final

Cada etapa alimenta a próxima. O resultado é uma proposta coerente, não um conjunto de partes soltas.

---

## Fluxo 1: Criação de conteúdo do zero

Este é o fluxo mais comum para quem trabalha com marketing, redes sociais ou comunicação.

**Situação:** Você precisa criar conteúdo para um tema específico, para uma plataforma específica, para um público específico.

**Etapa 1 — Definição estratégica:**
```
Vou criar conteúdo sobre [tema] para [público] no [canal]. Antes de gerar qualquer
texto, preciso definir a estratégia.

Me dê:
1. Os 3 principais ângulos/abordagens para este tema com este público
2. Para cada ângulo: o formato de post mais adequado (educativo, storytelling,
   prova social, provocação, etc.)
3. Uma sugestão de sequência lógica para os 3 posts

Público: donos de salão de beleza de pequeno porte, 30-50 anos, interior do Brasil,
têm pouca experiência com digital.
Tema: como usar o WhatsApp para fidelizar clientes.
```

**Etapa 2 — Desenvolvimento de cada post (um por vez):**
```
Com base no ângulo 1 (educativo sobre o problema), escreva o post completo.

Especificações:
- Plataforma: Instagram
- Tamanho: 150-200 palavras
- Estrutura: gancho + desenvolvimento + CTA
- Tom: prático, direto, sem jargão técnico
- Inclua emojis estratégicos (máximo 5)
```

**Etapa 3 — Revisão de coerência:**
```
Aqui estão os 3 posts que geramos. Revise a coerência entre eles:
- A linguagem está uniforme?
- A progressão faz sentido (problema → solução → resultado)?
- Alguma mudança de tom que precisa ser ajustada?
- Qual CTA está mais fraco e como melhorar?

[COLE OS 3 POSTS]
```

---

## Fluxo 2: Escrita de proposta comercial

**Situação:** Você teve uma reunião com um cliente potencial e precisa enviar uma proposta que converta.

**Etapa 1 — Briefing:**
```
Vou criar uma proposta comercial. Primeiro, vou te dar o contexto completo.
Por enquanto, apenas confirme que entendeu e aguarde minha instrução.

Contexto:
- Cliente: [nome], dono de [tipo de negócio] em [cidade]
- Problema relatado: [descreva o que ele disse na reunião]
- O que já foi discutido: [principais pontos da conversa]
- Meu serviço: [o que você oferece]
- Investimento: [valor ou faixa]
- Prazo de entrega: [prazo]
```

**Etapa 2 — Estrutura da proposta:**
```
Com base neste contexto, sugira a estrutura ideal para a proposta. Liste as seções
com uma linha descrevendo o objetivo de cada uma. Não escreva o conteúdo ainda.
```

**Etapa 3 — Seção por seção:**
```
Escreva a seção "Diagnóstico" da proposta. Esta seção deve mostrar que entendemos
profundamente o problema do cliente — usando as informações do briefing. Deve criar
empatia e identificação. Tom: consultivo e empático. 2-3 parágrafos.
```

(Repita para cada seção aprovada na Etapa 2)

**Etapa 4 — Revisão final:**
```
Leia a proposta completa abaixo e responda:
1. O argumento central está claro?
2. Onde a lógica de persuasão está mais fraca?
3. O CTA final é forte o suficiente?
4. Tem algum ponto que o cliente poderia questionar e que não está respondido?

[COLE A PROPOSTA COMPLETA]
```

---

## Fluxo 3: Análise e resposta a feedback de clientes

**Situação:** Você recebeu avaliações, reclamações ou feedbacks e quer entender o que fazer com eles.

**Etapa 1 — Análise dos feedbacks:**
```
Analise estes [N] feedbacks de clientes e me entregue:
1. As 3 reclamações mais frequentes (em ordem de frequência)
2. Os 3 elogios mais frequentes
3. O que mais surpreendeu — positivo ou negativo — que você não esperava encontrar

[COLE OS FEEDBACKS]
```

**Etapa 2 — Priorização de ações:**
```
Com base na análise, quais são as 3 mudanças que teriam maior impacto na
satisfação do cliente? Para cada uma: o que mudar, como medir se melhorou,
e qual é o esforço relativo (baixo/médio/alto)?
```

**Etapa 3 — Geração de respostas:**
```
Escreva uma resposta padrão para a reclamação mais frequente ([descreva]).
Requisitos:
- Tom: empático, sem ser defensivo
- Reconheça o problema sem admitir falha legal
- Ofereça uma solução concreta
- Máximo 100 palavras
- Inclua uma versão mais formal (e-mail) e uma mais casual (WhatsApp)
```

---

## Fluxo 4: Preparação para uma reunião ou apresentação

**Situação:** Você tem uma reunião importante e quer chegar preparado.

**Etapa 1 — Mapeamento de possíveis objeções:**
```
Vou apresentar esta proposta/ideia para [perfil da pessoa].
Me dê as 7 objeções mais prováveis que ela vai levantar, em ordem de importância.
Para cada objeção: como responderia de forma clara e não defensiva?

Proposta/ideia: [descreva em 3-5 linhas]
Perfil: [quem é, qual cargo, qual contexto, o que ela tipicamente valoriza]
```

**Etapa 2 — Preparação de perguntas:**
```
Quais são as 5 perguntas que eu devo fazer nessa reunião para entender melhor
as necessidades e desejos dessa pessoa, de forma que eu possa adaptar a proposta
durante a conversa?
```

**Etapa 3 — Simulação de diálogo:**
```
Vamos simular a reunião. Você é [nome/cargo]. Eu vou apresentar a ideia e você
vai reagir como essa pessoa reagiria — com as dúvidas, o ceticismo e os interesses
que são típicos desse perfil. Comece fazendo a primeira pergunta ou comentário
após eu apresentar a ideia. Pronto? Começo: [sua abertura de apresentação]
```

---

## Como manter contexto entre prompts

O maior desafio em fluxos é o contexto: como garantir que o prompt da etapa 3 "lembre" do que foi definido na etapa 1?

**Opção 1 — Resumo de handoff**

Ao final de cada etapa, peça um resumo das decisões tomadas:

```
Resuma em 5 bullets as principais decisões que tomamos nesta etapa. Vou usar
esse resumo para carregar no próximo prompt.
```

No prompt seguinte, cole esse resumo como contexto inicial.

**Opção 2 — Sessão única com etapas marcadas**

Em vez de sessões separadas, use uma só sessão e marque as etapas claramente. O modelo vai manter o histórico da conversa.

Desvantagem: sessões muito longas perdem eficiência perto do limite da janela de contexto.

**Opção 3 — Documento de contexto permanente**

Para projetos que se estendem por várias sessões, crie um documento de contexto — um arquivo de texto que você atualiza e cola no início de cada sessão nova.

O documento deve conter:
- O objetivo do projeto
- Decisões já tomadas
- O que foi produzido
- Próximos passos

Isso substitui a memória que o modelo não tem.

---

## Sinais de que seu fluxo está funcionando

Um fluxo bem construído tem estas características:

- Cada etapa produz um output que você pode avaliar independentemente
- A qualidade do output final é superior ao que seria em um único prompt grande
- Você consegue identificar exatamente em qual etapa algo deu errado, se der
- As etapas seguem uma lógica natural — nenhuma depende de informação que ainda não foi gerada

Quando um fluxo não funciona, geralmente é porque:
- A etapa 1 não forneceu contexto suficiente para as etapas seguintes
- Etapas que deveriam ser sequenciais foram fundidas em uma só
- O contexto não foi adequadamente carregado entre etapas

---

## Fluxos para rotinas recorrentes

Os fluxos mais valiosos são os que você usa toda semana. Quando um fluxo está bem ajustado, você pode executar a mesma sequência repetidamente com mínimo esforço.

Exemplos de fluxos recorrentes:

**Fluxo semanal de conteúdo:**
1. Análise do que performou na semana anterior
2. Geração de temas para a semana com base nos temas de melhor performance
3. Geração dos posts por tema
4. Revisão de coerência e ajuste

**Fluxo de proposta comercial:**
1. Briefing do cliente (sempre o mesmo formato)
2. Geração da proposta por seções (sequência fixa)
3. Revisão e ajuste final

**Fluxo de atendimento a reclamações:**
1. Análise da reclamação e categorização
2. Identificação da resposta padrão correspondente
3. Personalização da resposta ao cliente específico

Quando esses fluxos estão no seu banco de prompts (Aula 7), você executa cada um em minutos.

---

## Erros comuns

**Erro 1: Tentar fazer tudo em um prompt**
"Crie minha estratégia de marketing, o calendário de outubro com 20 posts, a legenda de cada post e a imagem de cada um." Isso vai gerar rascunhos rasos de tudo. Faça um item por vez.

**Erro 2: Perder o contexto entre etapas**
Gerar a estratégia em uma sessão e os posts em outra, sem carregar o contexto. Os posts vão ignorar a estratégia porque o modelo não sabe que ela existe.

**Erro 3: Não avaliar antes de avançar**
Passar para a etapa 2 sem verificar se a etapa 1 está certa. Se a etapa 1 definiu algo errado, as próximas etapas vão desenvolver em cima de uma base ruim.

**Erro 4: Fluxos longos demais sem checkpoints**
Um fluxo com 10 etapas sem pausa para avaliar pode gerar um resultado final excelente ou um resultado final ruim — você só descobre no final. Avalie em pontos críticos, especialmente após etapas de definição estratégica.

**Erro 5: Não documentar o fluxo que funcionou**
Quando você encontra uma sequência que produz bons resultados, documente. Anote cada prompt, o que você adaptou, o que funcionou. Isso constrói seu repertório (mais sobre isso na Aula 7).

---

## Exercício prático

Escolha um entregável que você precisa produzir na próxima semana — uma proposta, um conjunto de posts, um documento, um plano.

1. Liste as etapas lógicas para chegar ao produto final
2. Identifique quais etapas dependem das anteriores
3. Escreva o prompt para a primeira etapa usando os componentes da Aula 2
4. Execute a etapa 1, avalie o resultado, então execute a etapa 2
5. Ao final, compare o resultado do fluxo com o que teria sido produzido em um único prompt grande

Documente a sequência completa para usar de novo.

---

## Resumo

- Um fluxo é uma sequência de prompts que produz um entregável completo — diferente de um prompt isolado.
- O princípio da decomposição: divida o projeto em etapas menores com outputs avaliáveis.
- Principais fluxos de uso: criação de conteúdo, proposta comercial, análise de feedback, preparação para reunião.
- O contexto precisa ser mantido entre etapas: via resumo de handoff, sessão única, ou documento de contexto permanente.
- Avalie cada etapa antes de avançar — erros de definição na etapa 1 se multiplicam nas etapas seguintes.
- Fluxos recorrentes documentados são o maior multiplicador de produtividade com IA.
