# Aula 6 — Prompts para Tarefas de Negócio

## O que você vai entender nesta aula

Esta aula é um guia prático de prompts para as tarefas mais comuns de qualquer negócio: comunicação com clientes, criação de conteúdo, vendas, análise e operação. Para cada categoria, você vai aprender a estrutura do prompt, o mecanismo que explica por que funciona, e exemplos concretos que você pode usar hoje — adaptando para o seu contexto.

---

## Comunicação com clientes

A comunicação com clientes consome tempo desproporcional ao valor gerado quando feita manualmente, mensagem por mensagem, sem padrão. A IA resolve isso sem perder a personalização.

### E-mails de follow-up e cobrança

O e-mail de follow-up tem um desafio específico: ser insistente sem parecer inconveniente, firme sem parecer agressivo.

**Prompt para follow-up após proposta enviada:**
```
Escreva um e-mail de follow-up para um cliente que recebeu minha proposta há 7 dias
e não respondeu. A proposta era de [descreva o serviço] por [valor].

Contexto: a reunião inicial foi boa, o cliente demonstrou interesse, mas ficou de
"ver melhor" e não deu retorno.

Tom: cordial e direto. Não seja insistente ou ansioso. Ofereça valor adicional
na mensagem — compartilhe um insight ou dica relevante relacionada ao serviço.

Formato:
- Assunto do e-mail
- Corpo com máximo 150 palavras
- CTA claro no final (pergunta específica, não "aguardo retorno")
```

**Prompt para cobrança de fatura atrasada:**
```
Escreva uma mensagem de cobrança de WhatsApp para cliente com fatura de R$[valor]
atrasada há [X] dias. Nossa relação é [boa/neutra/nova].

Restrições:
- Tom: educado mas claro — sem rodeios
- Não use termos jurídicos ou ameaças
- Ofereça pix como opção de pagamento imediato
- Máximo 80 palavras
- Termine com uma pergunta que facilite a resposta (tem algum imprevisto? posso ajudar de alguma forma?)
```

**Por que funciona:** Definir o tom explicitamente ("não seja ansioso", "firme mas cordial") direciona o modelo para calibrar a linguagem corretamente. O CTA específico evita o genérico "aguardo retorno" que raramente gera resposta.

---

### Respostas a objeções de vendas

Objeções são o momento mais crítico de uma venda. A resposta certa converte; a resposta errada encerra o diálogo.

**Prompt para responder objeção de preço:**
```
Um potencial cliente respondeu à minha proposta dizendo: "Seu preço está acima
do que esperávamos. Temos outras propostas mais em conta."

Escreva uma resposta para WhatsApp que:
1. Não baixe o preço imediatamente
2. Reforce o valor diferencial do meu serviço
3. Faça uma pergunta que abra diálogo sobre o que ele está comparando
4. Tom: confiante, sem ser arrogante

Meu diferencial é: [descreva o que te diferencia dos concorrentes]
Máximo 120 palavras.
```

**Prompt para responder "vou pensar":**
```
Cliente respondeu "vou pensar e te falo" após apresentação de proposta.

Crie uma mensagem de resposta para WhatsApp que:
1. Respeite o espaço dele sem desaparecer
2. Ofereça um próximo passo claro (uma ligação de 15 min? uma pergunta específica?)
3. Adicione um elemento de urgência legítima (não fake)
4. Tom: descontraído e seguro

[Urgência real que posso usar: por exemplo, "tenho uma vaga disponível agora, mas tenho outra proposta para a semana que vem"]
Máximo 100 palavras.
```

---

### Scripts de atendimento

Scripts não são para robotizar o atendimento — são para garantir que as mensagens importantes sejam ditas corretamente, mesmo nos momentos de pressão.

**Prompt para script de primeiro contato (leads que perguntam o preço):**
```
Crie um script de WhatsApp para responder leads que chegam perguntando "Qual é
o preço do serviço X?"

Objetivo: não dar o preço de imediato, entender a necessidade primeiro e
qualificar o lead antes de apresentar a proposta.

O script deve ter 3 etapas:
1. Acolhimento e confirmação de interesse
2. 2-3 perguntas para qualificar (o que precisa, qual prazo, já tentou outras
   soluções)
3. Promessa do próximo passo (enviar proposta personalizada em até X horas)

Tom: acolhedor, profissional, sem parecer script (linguagem natural)
```

---

## Criação de conteúdo

Conteúdo é o maior gargalo para quem trabalha solo ou em equipe pequena. A IA não substitui a estratégia — mas elimina o tempo de produção.

### Posts para Instagram

**Prompt para post educativo (o mais comum e mais fácil de errar):**
```
Escreva um post educativo para Instagram sobre [tema]. Público: [descreva].

Estrutura:
- Linha 1: gancho que para o scroll (pergunta, afirmação surpreendente ou dado)
- Corpo: 3-4 tópicos curtos e práticos (use emojis para separar)
- Final: CTA com pergunta para gerar comentários

Tom: [direto/acolhedor/técnico] — como [comparação de estilo]
Tamanho: 150-200 palavras
Não use: jargão de marketing, frases motivacionais genéricas
```

**Prompt para post de prova social:**
```
Crie um post baseado neste resultado de cliente para Instagram.

Resultado: [descreva o resultado concreto — exemplo: "cliente passou de 2 para
8 agendamentos por semana em 30 dias"]

O post deve:
1. Abrir com o resultado (não com "cliente chegou até mim dizendo...")
2. Contextualizar brevemente o problema que existia antes
3. Mencionar o processo de forma geral (sem revelar detalhes estratégicos)
4. Fechar com uma pergunta que conecta com quem tem o mesmo problema

Sem nome do cliente (não tenho autorização). Tom: profissional mas próximo.
```

**Prompt para carrossel:**
```
Crie um roteiro de carrossel de 7 slides sobre [tema].

Estrutura de cada slide:
- Slide 1: título do carrossel + gancho visual (descreva a imagem ideal)
- Slides 2-6: um ponto por slide (título do slide + 2-3 linhas de conteúdo)
- Slide 7: CTA

Cada slide máximo 40 palavras de texto. Foque em [o principal problema que o
público tem com esse tema]. Torne cada slide autoexplicativo — alguém que viu
só aquele slide entende o ponto.
```

---

### Planejamento de conteúdo

**Prompt para calendário editorial mensal:**
```
Crie um calendário editorial de 20 posts para [mês] para [tipo de negócio].
Público: [descreva].

Distribuição desejada:
- 40% conteúdo educativo (problema/solução)
- 30% prova social (resultados, depoimentos)
- 20% conteúdo de bastidores/humanização
- 10% oferta direta

Para cada post, informe:
- Data sugerida
- Tipo de conteúdo
- Tema específico
- Formato (feed, stories, reels, carrossel)
- Gancho sugerido (1 frase)

Considere [eventos/datas relevantes do mês, se houver].
```

---

## Vendas e propostas

### Proposta comercial

**Prompt para seção de diagnóstico (a mais importante da proposta):**
```
Escreva a seção "Diagnóstico" de uma proposta comercial para [nome do cliente].

Esta seção deve mostrar que entendemos profundamente o problema dele — usando
APENAS as informações abaixo. Não invente problemas que ele não mencionou.

Informações coletadas na reunião:
- Principal problema relatado: [descreva]
- Consequências que ele mencionou: [descreva]
- O que ele já tentou: [descreva]
- O que ele busca alcançar: [descreva]

Objetivo da seção: criar identificação total. O cliente deve ler e pensar
"é exatamente assim que me sinto". Não seja genérico. Seja específico.

Tom: consultivo, empático. 3-4 parágrafos.
```

**Prompt para seção de investimento (onde a maioria erra):**
```
Escreva a seção "Investimento" de uma proposta comercial que apresenta um valor
de R$[valor] por mês.

Esta seção deve:
1. Apresentar o valor como investimento, não como custo
2. Contextualizar o valor em relação ao resultado esperado
3. Mostrar o que está incluído de forma clara (não uma lista seca)
4. Incluir uma garantia ou redução de risco se existir

O que está incluído: [liste o que o serviço engloba]
Resultado esperado / ROI: [descreva o que o cliente pode esperar]
Garantia (se houver): [descreva]
```

---

### Scripts de vendas

**Prompt para script de discovery call (primeira ligação de vendas):**
```
Crie um script de 15 minutos para uma discovery call com [perfil do lead].

Estrutura:
1. Abertura (2 min): rapport + objetivo da call
2. Qualificação (5 min): 4-5 perguntas para entender o problema
3. Apresentação de valor (5 min): como posso ajudar, de forma geral
4. Próximos passos (3 min): agendamento de apresentação ou envio de proposta

Para cada seção: o que dizer + dica de como dizer + possíveis respostas do prospect.
Tom: consultivo, não vendedor. O objetivo não é vender na call — é qualificar.
```

---

## Análise e diagnóstico de negócio

### Análise de dados simples

**Prompt para análise de métricas de negócio:**
```
Analise estes dados do meu negócio e me dê um diagnóstico honesto.

Dados do último mês:
- Faturamento: R$[valor]
- Número de clientes ativos: [N]
- Ticket médio: R$[valor]
- Taxa de conversão de leads: [X]%
- Leads recebidos: [N]
- Clientes que saíram: [N]

Perguntas:
1. O que está saudável nestes números?
2. O que é preocupante?
3. Qual é o indicador que merece atenção urgente?
4. Se você tivesse que sugerir uma ação para o próximo mês, qual seria?
```

**Prompt para análise competitiva rápida:**
```
Vou te dar informações sobre dois concorrentes diretos e meu negócio.
Faça uma análise comparativa identificando:
1. Onde estou melhor que os concorrentes
2. Onde estou em desvantagem
3. Uma oportunidade de diferenciação que nenhum dos três está explorando claramente

Meu negócio: [descreva posicionamento, preço, serviços]
Concorrente 1: [descreva]
Concorrente 2: [descreva]

Seja honesto — não me diga apenas o que quero ouvir.
```

---

### Operação e processos

**Prompt para criar um SOP (Procedimento Operacional Padrão):**
```
Escreva um SOP (procedimento passo a passo) para o processo de [nome do processo].

O SOP deve ser seguido por [quem vai executar — você mesmo? um funcionário? um
freela?] que tem [nível de experiência com essa tarefa].

O processo começa quando [gatilho] e termina quando [resultado entregue].

Passos que eu sei que existem (não necessariamente em ordem):
[LISTE OS PASSOS QUE VOCÊ JÁ FAZ]

O SOP deve incluir:
- Passo a passo numerado
- Para cada passo crítico: o que pode dar errado e como resolver
- Tempo estimado de cada etapa
- Ferramentas necessárias
```

---

## Recrutamento e gestão

**Prompt para escrever uma descrição de vaga:**
```
Escreva uma descrição de vaga para [cargo] em [tipo de negócio].

O candidato ideal: [descreva habilidades, experiência, perfil comportamental]
O que a vaga oferece: [salário ou faixa, benefícios, modelo de trabalho]
O que NÃO incluir: linguagem corporativa genérica, bullet points sem vida

A descrição deve:
1. Atrair pessoas com o perfil certo (ser específica o suficiente para filtrar)
2. Apresentar a empresa de forma honesta e humana
3. Descrever o dia a dia real, não só as responsabilidades formais

Tom: humano e direto. Se for um ambiente informal, que apareça no texto.
Máximo 350 palavras.
```

**Prompt para roteiro de entrevista:**
```
Crie um roteiro de entrevista para avaliar [cargo].

As competências mais importantes para essa posição são:
1. [Competência 1]
2. [Competência 2]
3. [Competência 3]

Para cada competência, crie:
- 1 pergunta situacional ("Me conte uma vez em que você...")
- 1 pergunta de julgamento ("O que você faria se...")
- O que uma resposta forte soa versus uma resposta fraca

Inclua também 3 perguntas sobre valores/cultura, relevantes para [tipo de empresa/
equipe que você tem].
```

---

## Erros comuns

**Erro 1: Usar prompts genéricos para tarefas de negócio**
"Escreva um e-mail de vendas" vai gerar um e-mail de vendas genérico. "Escreva um e-mail de follow-up para um lead que assistiu meu webinar de consultoria financeira para MEIs mas não agendou a sessão de diagnóstico" vai gerar algo relevante.

**Erro 2: Não revisar conteúdo antes de publicar**
A IA gera com fluidez — mas pode gerar imprecisões sutis, afirmações que não representam sua marca, ou frases que soam artificiais. Sempre leia antes de enviar.

**Erro 3: Usar prompts de negócio sem context de público**
Um e-mail para um executivo de grande empresa e um e-mail para um dono de salão no interior precisam de tons completamente diferentes. O contexto do público é essencial.

**Erro 4: Esperar que a IA conheça seu negócio**
A IA não sabe que você tem uma garantia, que seu prazo é diferente do mercado, que seu diferencial é X. Se não está no prompt, não aparece no resultado.

**Erro 5: Tratar todos os e-mails como iguais**
Um e-mail de boas-vindas, um e-mail de cobrança e um e-mail de proposta têm objetivos completamente diferentes. O prompt precisa refletir o objetivo específico.

---

## Exercício prático

Identifique a tarefa de comunicação que mais consome seu tempo no negócio. Pode ser:
- Responder perguntas de preço
- Escrever propostas
- Criar posts para Instagram
- Responder reclamações

Use a estrutura desta aula para criar um prompt específico para essa tarefa. Execute, avalie, refine.

Depois, salve o prompt final — ele vai direto para o banco de prompts da Aula 7.

---

## Resumo

- Prompts de negócio exigem contexto específico — quem é o cliente, qual é o objetivo, qual é o tom para aquele público.
- Para comunicação com clientes: defina o tom explicitamente e inclua um CTA específico (não "aguardo retorno").
- Para conteúdo: especifique a estrutura (gancho + corpo + CTA) e as restrições de formato.
- Para propostas: a seção de diagnóstico é a mais importante — ela precisa usar as informações específicas do cliente, não ser genérica.
- Para análise: forneça os dados reais e peça um diagnóstico honesto — incluindo o que não está funcionando.
- Para scripts: inclua não apenas o que dizer, mas como dizer e o objetivo de cada etapa.
- A personalização ao contexto específico é o que separa um prompt útil de um prompt genérico.
