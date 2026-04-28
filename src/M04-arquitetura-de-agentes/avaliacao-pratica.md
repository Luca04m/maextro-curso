# Avaliação Prática — Módulo 4: Arquitetura de Agentes & Automação Inteligente

## Objetivo da Avaliação

Validar que você não apenas entendeu os conceitos, mas que consegue construir e operar automações reais. O módulo é concluído quando você tem um agente funcionando que resolve um problema do seu trabalho — não quando você terminou de ler.

---

## Estrutura da Avaliação

A avaliação é composta por três partes:

- **Parte 1** — Automação básica validada (obrigatória)
- **Parte 2** — Agente produtivo completo (obrigatória)
- **Parte 3** — Análise de impacto (obrigatória)

---

## Parte 1: Automação Básica

### O que você entrega

Uma automação de pelo menos 3 etapas, rodando no Make, que resolve um problema real e recorrente do seu trabalho.

### Critérios obrigatórios

**1. Problema real documentado**
Descreva em 3-5 frases:
- Qual é o processo manual atual?
- Com que frequência ele ocorre?
- Quanto tempo leva por ocorrência?

*Exemplo aceitável*: "Todo formulário preenchido no meu site vai para o e-mail. Eu leio, copio o contato para uma planilha e mando e-mail de resposta manual. Acontece em média 5 vezes por semana, leva 10 minutos cada."

*Exemplo não aceitável*: "Quero automatizar meu trabalho." (vago demais, sem problema específico)

**2. Fluxo com pelo menos 3 módulos**

O cenário deve ter:
- Um gatilho (o que inicia)
- Pelo menos uma condição ou filtro
- Pelo menos duas ações

**3. Histórico de execuções**

Print do histórico do Make mostrando no mínimo 5 execuções bem-sucedidas com dados reais (não de teste).

**4. Nenhuma execução com erro nos últimos 3 dias**

O fluxo deve estar estável. Erros esporádicos são normais; erros consistentes indicam problema não resolvido.

---

## Parte 2: Agente Produtivo Completo

### O que você entrega

O Assistente de Atendimento e Qualificação da Aula 6, ou uma variação equivalente que combine:
- Captura de dados estruturada
- Processamento por IA (OpenAI ou equivalente)
- Lógica condicional (pelo menos 2 caminhos diferentes)
- Registro em banco de dados (Google Sheets ou similar)
- Notificação para você

### Critérios obrigatórios

**1. Formulário publicado e funcional**

Link do formulário acessível. Deve ter no mínimo 5 campos com informações relevantes para qualificação.

**2. Prompt de qualificação personalizado**

O prompt deve usar seu ICP real (não o exemplo genérico da aula). Deve incluir:
- Critérios específicos do seu nicho/serviço
- Seu tom de voz
- Formato de saída estruturado (JSON)

**3. Roteamento por qualificação**

Pelo menos 3 caminhos diferentes com ações distintas. Mostre o diagrama no Make com os 3 caminhos visíveis.

**4. Registro no CRM**

Print da planilha de CRM com pelo menos 6 leads de teste registrados, com todos os campos preenchidos corretamente.

**5. Notificações funcionando**

Print das notificações recebidas (Telegram ou e-mail) para cada categoria de lead.

**6. Avaliação de qualidade das mensagens geradas**

Para 3 das mensagens geradas pelo agente, faça uma avaliação:
- A mensagem menciona especificamente o problema declarado pelo lead?
- O tom está alinhado com sua comunicação natural?
- Você enviaria essa mensagem com menos de 2 minutos de edição?

Se a resposta para qualquer uma for "não", você ainda precisa ajustar o prompt antes de considerar completo.

---

## Parte 3: Análise de Impacto

### O que você entrega

Um documento de 1 página (pode ser Google Docs) respondendo:

**1. Tempo economizado**

Com base no tempo manual antes da automação e no número de execuções nos últimos 7 dias:
- Tempo manual por ocorrência: X minutos
- Execuções nos últimos 7 dias: Y vezes
- Tempo total economizado: X × Y = Z minutos

**2. Qualidade vs manual**

O output do agente é melhor, igual ou pior que o manual? Em quais dimensões?

*Dimensões para avaliar*: velocidade de resposta, consistência, personalização, erros.

**3. O que você aprendeu sobre seus limites**

Qual parte do processo você tentou automatizar e descobriu que não funcionava bem? Por quê? Essa é uma das perguntas mais valiosas — entender onde a automação não funciona é tão importante quanto entender onde funciona.

**4. Próximo agente**

Com base no que você aprendeu, qual é o próximo processo que você vai automatizar? Por quê?

---

## Critérios de Conclusão do Módulo

O Módulo 4 é concluído quando você atender a TODOS os critérios abaixo:

| Critério | Validação |
|---------|-----------|
| Automação básica rodando há pelo menos 7 dias sem erros | Print do histórico |
| Agente produtivo com todas as 6 partes funcionando | Print do cenário + planilha + notificações |
| Prompt de qualificação personalizado (não genérico) | Mostrar o prompt |
| Pelo menos 5 execuções de teste com dados reais | Print do histórico |
| Análise de impacto documentada | Documento com as 4 respostas |
| Pelo menos 1 ajuste de prompt feito após feedback de teste | Descrever o ajuste e por quê |

---

## O que NÃO é critério de conclusão

- Perfeição: o agente não precisa ser perfeito, precisa ser funcional e útil
- Custo zero: se você precisou pagar R$20 no Make ou US$5 na OpenAI, tudo bem
- Velocidade: se levou 3 semanas para construir e funcionar, tudo bem — o que importa é funcionar

---

## Formato de entrega

Não existe uma plataforma de entrega — esse módulo é para você. A "entrega" é o próprio agente rodando no Make e a análise documentada no seu Google Docs.

Use esses critérios como um checklist pessoal. Quando todos os itens estiverem marcados, você concluiu o módulo e está pronto para o Módulo 5.

---

## Referência de diagnóstico

Se você está travado em algum ponto, use esse guia:

**"O Make não conecta com o Google"**
Verifique se você está logado na conta correta do Google. Desconecte e reconecte a integração.

**"O JSON retornado pela OpenAI está quebrando o módulo seguinte"**
Adicione no prompt: "Retorne APENAS o JSON válido, sem texto antes ou depois, sem markdown." Use o módulo Tools → JSON Parse com tratamento de erro.

**"O fluxo roda mas não envia e-mail"**
Verifique as permissões da conexão Gmail. Às vezes é necessário revogar e reconectar.

**"A qualificação está classificando todo lead como COLD"**
Seu prompt de ICP pode estar muito restritivo, ou o campo de orçamento do formulário não está sendo mapeado corretamente. Teste o prompt diretamente no ChatGPT com dados reais para verificar se o problema é o prompt ou o mapeamento.

**"O agente está gerando mensagens genéricas demais"**
O prompt precisa de mais contexto específico: qual é seu posicionamento, que resultados você entrega, que tipo de cliente você atende. Quanto mais específico o contexto, mais específica a mensagem.

---

## Nota sobre custo

A construção completa deste módulo deve custar entre R$0 e R$30 no total (dependendo de quantas chamadas de API da OpenAI você fizer durante os testes).

- Make gratuito: R$0
- OpenAI: ~US$0.01-0.05 por qualificação completa com GPT-4o mini (o modelo mais barato). Para 20 testes: US$1
- Typeform gratuito: R$0
- Calendly gratuito: R$0

Se você está gastando mais do que isso, provavelmente está usando um modelo caro onde um mais barato resolveria. GPT-4o mini resolve qualificação de leads perfeitamente a uma fração do custo do GPT-4o.
