# Aula 6 — Construindo seu Primeiro Agente Produtivo

## O que você vai entender nesta aula

Você vai construir um agente produtivo completo e funcional — do zero ao rodando. Não é um exercício acadêmico: é um sistema que vai trabalhar para você a partir de hoje. O projeto é um **Assistente de Atendimento e Qualificação** que gerencia contatos iniciais, qualifica leads, prepara respostas personalizadas e mantém seu CRM atualizado, funcionando 24 horas por dia.

---

## 1. O que torna um agente "produtivo"

Antes de construir, precisamos definir o que significa produtivo. Um agente produtivo tem três características:

**Resolve um problema real e recorrente.** Não é demonstração — é solução. O problema existe hoje, custa tempo real, e acontece com frequência suficiente para justificar o investimento de construir.

**Opera de forma confiável, não apenas impressionante.** Um agente que funciona 90% das vezes e falha 10% pode ser pior do que não ter agente nenhum — especialmente quando a falha envolve comunicação com clientes. Confiabilidade primeiro.

**Entrega output que você usaria.** Se você precisa reescrever 80% do que o agente produziu, o agente não está entregando valor real. O agente deve produzir algo que você usa com ajustes menores, não do zero.

Com essas três características em mente, vamos para o projeto.

---

## 2. O Projeto: Assistente de Atendimento e Qualificação

### O que ele faz

Quando um potencial cliente entra em contato (via formulário de site, e-mail, ou mensagem), o agente:

1. Recebe o contato e extrai as informações relevantes
2. Pesquisa no seu histórico se é um contato conhecido
3. Qualifica o lead com base em critérios que você define
4. Gera uma resposta personalizada com o próximo passo adequado
5. Registra tudo no seu CRM (planilha Google Sheets)
6. Notifica você com um resumo da situação

O resultado: você recebe uma notificação que diz "Lead HOT chegou: João Silva, empresa X, orçamento Y, já enviei resposta inicial e agendei para calendário. Revisar rascunho em Gmail."

Você abre o Gmail, vê o rascunho, aprova ou ajusta, e manda. Todo o trabalho de triagem, qualificação, pesquisa de histórico e geração de resposta foi feito pelo agente.

### Por que esse projeto específico

- Problema real e universal para qualquer profissional solo
- Combina múltiplos conceitos das aulas anteriores
- Tem impacto imediato no tempo economizado
- Demonstra as capacidades centrais de um agente: percepção, raciocínio, ação, memória

---

## 3. Arquitetura do agente

Antes de montar o fluxo, visualize a arquitetura completa:

```
[Fonte de entrada] 
    → [Extração e normalização dos dados]
    → [Consulta ao histórico]
    → [Qualificação por IA]
    → [Roteamento por classificação]
        → Caminho HOT: resposta urgente + agendamento + alerta
        → Caminho WARM: resposta padrão + tarefa de follow-up
        → Caminho COLD: resposta educacional + lista de nutrição
    → [Registro no CRM]
    → [Notificação para você]
```

Esse é o diagrama mental. No Make, cada caixa vira um módulo.

---

## 4. Preparação: o que você vai precisar

Antes de abrir o Make, prepare:

### Contas e acessos

- **Make** (make.com) — conta gratuita
- **Google Workspace** — Gmail + Google Sheets + Google Docs
- **OpenAI** — conta com créditos (você recebe créditos ao criar conta; a construção e testes iniciais custam centavos)
- **Typeform** — conta gratuita (formulário mais sofisticado que Google Forms, com lógica condicional)
- **Calendly** — conta gratuita (para agendamento automático)
- **Telegram** — para notificações (gratuito; crie um bot via @BotFather)

### Documentos de referência (você cria antes)

**1. Perfil Ideal de Cliente (ICP)**

Uma planilha simples com: setor, tamanho de empresa, faixa de orçamento mínimo, problemas que você resolve, problemas que você não resolve. O agente vai usar isso para qualificar.

Exemplo:
- Setores: marketing, e-commerce, serviços B2B
- Orçamento mínimo: R$2.000/mês
- Problema principal: gerar leads qualificados ou aumentar conversão
- Não atendo: empresas com produto ainda em ideação, orçamento mensal abaixo de R$1.500

**2. Contexto da sua oferta**

Um parágrafo descrevendo o que você oferece, para quem, e qual resultado típico você entrega. O agente vai usar isso para escrever respostas relevantes.

**3. Tom de voz**

3-5 adjetivos que descrevem como você se comunica: "profissional mas acessível, direto, sem jargão excessivo, orientado a resultado".

---

## 5. Construindo o fluxo — passo a passo

### BLOCO 1: Entrada de dados

**Módulo 1.1 — Gatilho: Typeform → New Entry**

Configure um formulário de "aplicação para serviços" com:
- Nome completo (obrigatório)
- E-mail (obrigatório)
- Empresa (obrigatório)
- Setor da empresa
- Qual seu principal desafio de marketing hoje? (campo de texto longo)
- O que você já tentou para resolver esse desafio?
- Qual resultado você espera alcançar em 3 meses?
- Qual é o investimento mensal disponível para marketing? (opções: até R$1.000 / R$1.000-R$3.000 / R$3.000-R$7.000 / mais de R$7.000)

Por que Typeform? Permite lógica condicional nas perguntas (mostrar pergunta B dependendo da resposta em A), o que resulta em dados mais ricos.

### BLOCO 2: Verificação de histórico

**Módulo 2.1 — Ação: Google Sheets → Search Rows**

Conecte sua planilha de CRM. Configure para buscar a coluna "E-mail" pelo e-mail que chegou no formulário.

Isso retorna: é um contato novo ou já consta no seu histórico?

**Módulo 2.2 — Condição: contato existe?**

- Se SIM: buscar os dados históricos (interações anteriores, proposta enviada, etc.)
- Se NÃO: marcar como novo contato

Isso vai alimentar o contexto que o agente tem para gerar a resposta.

### BLOCO 3: Qualificação por IA

**Módulo 3.1 — Ação: OpenAI → GPT-4o (Create Completion)**

Esse é o coração do agente. Configure o prompt como:

```
Sistema: Você é um especialista em qualificação de leads para [SEU SERVIÇO/NICHO]. Analise este contato e forneça uma avaliação estruturada.

PERFIL IDEAL DO CLIENTE:
[Cole aqui o seu ICP que você preparou]

DADOS DO CONTATO:
Nome: {{nome}}
Empresa: {{empresa}}
Setor: {{setor}}
Desafio: {{desafio}}
O que já tentou: {{tentativas}}
Resultado esperado: {{resultado}}
Orçamento: {{orçamento}}
É contato existente: {{resultado do módulo 2}}
Histórico (se existente): {{dados do histórico}}

AVALIAÇÃO NECESSÁRIA:
1. Pontuação de fit (0-100): quanto esse lead se alinha ao perfil ideal
2. Categoria: HOT (80-100) / WARM (50-79) / COLD (0-49)
3. Pontos de fit (o que alinha):
4. Pontos de atenção (o que não alinha ou exige clareza):
5. Próximo passo recomendado:
6. Mensagem personalizada de primeiro contato (tom: {{seu tom de voz}}, 3 parágrafos, mencionando especificamente o desafio declarado)

FORMATO DE RESPOSTA: JSON com os campos:
{
  "pontuacao": número,
  "categoria": "HOT/WARM/COLD",
  "fit": ["ponto1", "ponto2"],
  "atencao": ["ponto1", "ponto2"],
  "proximo_passo": "texto",
  "mensagem": "texto completo da mensagem"
}
```

Pedir o output em JSON é fundamental. Permite que os módulos seguintes extraiam cada campo de forma confiável.

**Módulo 3.2 — Ação: Tools → JSON Parse**

Converta o texto JSON retornado pelo OpenAI em dados estruturados. Agora você tem variáveis separadas para `pontuacao`, `categoria`, `mensagem`, etc.

### BLOCO 4: Roteamento

**Módulo 4.1 — Router com 3 caminhos**

**Caminho HOT (categoria = "HOT"):**

Módulo 4A.1 — Gmail → Create Draft
- Para: {{e-mail do lead}}
- Assunto: "Re: Sua aplicação — {{nome da empresa}}"
- Corpo: {{mensagem gerada pela IA}}

Módulo 4A.2 — Gmail → Send an Email (e-mail de notificação urgente para você)
"LEAD HOT: {{nome}} / {{empresa}} / Orçamento: {{orçamento}}. Rascunho preparado para revisão. Pontuação: {{pontuacao}}. Próximo passo: {{proximo_passo}}"

Módulo 4A.3 — Calendly (via HTTP Request) ou Google Calendar → Block time
Criar um evento de "Follow-up HOT: {{nome}}" no seu calendário para amanhã de manhã

Módulo 4A.4 — Telegram → Send Message (alerta urgente)

**Caminho WARM (categoria = "WARM"):**

Módulo 4B.1 — Gmail → Send an Email
Enviar diretamente a mensagem gerada pela IA (sem revisão para WARM — depois de calibrar, você pode confiar no padrão)

Módulo 4B.2 — Google Tasks → Create Task
"Follow-up WARM: {{nome}} / {{empresa}} — em 3 dias"

Módulo 4B.3 — Telegram → Send Message (notificação padrão)

**Caminho COLD (categoria = "COLD"):**

Módulo 4C.1 — Gmail → Send an Email
Uma mensagem padrão de "obrigado pelo contato + recurso gratuito relevante" (você cria esse template uma vez)

Módulo 4C.2 — Google Sheets → Add Row na aba "Nutrição"

### BLOCO 5: Registro no CRM

**Módulo 5.1 — Google Sheets → Add Row (ou Update Row se já existia)**

Registre na planilha de CRM:
- Data/hora
- Nome, e-mail, empresa, setor
- Pontuação de qualificação
- Categoria
- Pontos de fit
- Pontos de atenção
- Status: "Contato inicial enviado"

### BLOCO 6: Notificação final

**Módulo 6.1 — Telegram → Send Message**

```
✅ Processamento completo
Lead: {{nome}} / {{empresa}}
Categoria: {{categoria}} | Pontuação: {{pontuacao}}
Orçamento declarado: {{orçamento}}
Desafio: {{desafio}}
Ação tomada: {{ação correspondente à categoria}}
```

---

## 6. Configurando e testando

### Teste em 3 rodadas

**Rodada 1 — Teste técnico:**
Preencha o formulário com dados fictícios mas plausíveis, um para cada categoria esperada: um lead HOT (setor certo, orçamento alto, problema claro), um WARM (setor certo mas orçamento incerto), um COLD (setor errado ou orçamento muito baixo).

Verifique que cada caminho executa corretamente. Corrija problemas técnicos.

**Rodada 2 — Calibração do prompt:**
Olhe as mensagens geradas pelo agente. O tom está certo? A mensagem menciona o desafio de forma relevante? A qualificação faz sentido?

Ajuste o prompt conforme necessário. Essa é a parte que mais demanda iteração — não se preocupe se precisar de 5-10 rodadas de ajuste. É normal e necessário.

**Rodada 3 — Teste de stress:**
Preencha o formulário com:
- Campos faltando (deixe o orçamento em branco)
- Texto muito longo no campo de desafio
- Emoji e caracteres especiais no nome
- E-mail que já existe no CRM

Verifique que o fluxo lida com esses casos sem quebrar. Adicione filtros e tratamentos de erro onde necessário.

### Ativação gradual

Não ative o fluxo imediatamente para produção. Siga essa progressão:

**Semana 1**: Fluxo ativo, mas todos os e-mails vão como rascunho (você aprova cada um). Monitore todos os outputs.

**Semana 2-3**: Se a qualidade está consistente, ative envio automático para COLD. Continue revisando WARM e HOT.

**Semana 4+**: Se WARM está consistentemente bom, ative envio automático também. Mantenha HOT como rascunho sempre — leads prioritários merecem sua atenção pessoal.

---

## 7. Métricas para avaliar o agente

Depois de 30 dias rodando, avalie:

**Precisão de qualificação:**
De todos os leads marcados como HOT, quantos % avançaram para reunião? Se for muito baixo (abaixo de 60%), o agente está qualificando como HOT demais — ajuste o threshold no prompt.

**Qualidade das mensagens:**
Das mensagens WARM enviadas automaticamente, qual foi a taxa de resposta? Compare com o período anterior (quando você respondia manualmente). Se a taxa caiu, o tom está errado.

**Tempo economizado:**
Calcule o tempo total do seu processo manual de atendimento inicial × número de leads processados pelo agente. Esse é o tempo que você recuperou.

**Taxa de erro:**
Quantas execuções quebraram ou produziram output inaceitável? Se for acima de 5%, há um problema de confiabilidade que precisa ser resolvido antes de escalar.

---

## 8. Evoluindo o agente

Esse é o ponto de partida, não o ponto final. Depois de validar a versão básica, você pode evoluir:

**Memória mais rica:**
Em vez de buscar apenas o e-mail no histórico, buscar o histórico completo de interações, propostas enviadas, e notas de reuniões anteriores. O agente vai gerar respostas muito mais contextualizadas para clientes recorrentes.

**Follow-up automático:**
Um segundo fluxo que monitora os leads HOT — se não houver resposta em 48 horas, envia automaticamente uma mensagem de acompanhamento.

**Análise de padrões:**
Uma vez por mês, você manda a planilha de leads para o Claude ou ChatGPT com a pergunta "o que os leads HOT que converteram têm em comum? O que os COLD têm em comum? Quais ajustes devo fazer no meu ICP?" Análise de dados grátis.

**Integração com videoconferência:**
Quando um HOT agenda reunião via Calendly, o fluxo automaticamente:
- Cria um documento de preparação com o perfil do lead
- Envia um e-mail de confirmação com o link da reunião
- Cria uma tarefa "Preparar para reunião com [nome]" para o dia anterior

---

## Erros comuns

### Erro 1: Tentar fazer o agente perfeito antes de ativar

Você passa semanas ajustando, nunca ativa, nunca recebe feedback real.

**Mecanismo**: Perfeição em desenvolvimento é inimiga da utilidade em produção. Você só descobre o que ajustar quando recebe feedback de casos reais.

**Como corrigir**: Defina "bom o suficiente para testar" como o critério de ativação. Ative no modo de revisão (rascunhos), colete feedback real, itere.

### Erro 2: Prompt muito longo e vago

Um prompt com 2.000 palavras cheio de "considere", "leve em conta", "pode ser que" não produz outputs consistentes.

**Mecanismo**: Prompts vagos têm muitos espaços de interpretação. O modelo preenche esses espaços diferente a cada execução.

**Como corrigir**: Seja específico e conciso. Se precisar de muita instrução, divida em múltiplos módulos de IA em sequência — cada um com um escopo menor e claro.

### Erro 3: Output JSON inconsistente

O OpenAI às vezes retorna o JSON com texto antes ou depois, ou com formatação ligeiramente diferente, quebrando o JSON Parse.

**Mecanismo**: LLMs não são determinísticos. Mesmo pedindo JSON, às vezes adicionam contexto.

**Como corrigir**: No prompt, instrua explicitamente: "Retorne APENAS o JSON, sem texto antes ou depois, sem markdown code blocks." E adicione tratamento de erro — se o JSON Parse falhar, notifique você em vez de deixar o fluxo quebrar silenciosamente.

### Erro 4: Esquecer de versionar a planilha de CRM

Você adiciona uma coluna na planilha de CRM sem avisar o fluxo. O Make ainda está mapeando a coluna antiga. Os dados vão para o lugar errado.

**Mecanismo**: O mapeamento de colunas no Make é por posição ou nome. Se você muda a estrutura da planilha, o mapeamento quebra.

**Como corrigir**: Nunca mude a estrutura da planilha sem atualizar o cenário do Make. Adicione novas colunas sempre ao final, nunca no meio.

### Erro 5: Não documentar o que o agente está fazendo para novos clientes

Um cliente novo pergunta "como você atende tão rápido?" e você não sabe explicar claramente o que o agente faz, gerando expectativas erradas.

**Mecanismo**: Automações invisíveis criam confusão quando clientes percebem que algo "não é manual".

**Como corrigir**: Prepare uma explicação simples do sistema. "Tenho um processo de triagem que garante que todo contato receba uma resposta inicial em até X minutos, e que eu reviso pessoalmente antes de responder em detalhes." Transparência sobre o processo profissionaliza, não diminui.

---

## 9. Operações: mantendo o agente funcionando no longo prazo

Criar o agente é uma parte do trabalho. Mantê-lo funcionando de forma confiável por semanas e meses é outra — e frequentemente mais importante.

### Revisão semanal (10 minutos)

Toda segunda-feira, antes de começar o dia:
- Abra o Make, veja o histórico de execuções da semana anterior
- Alguma execução falhou? Qual módulo? Por quê?
- O volume de execuções está dentro do esperado? (muito abaixo pode indicar que o gatilho não está disparando; muito acima pode indicar um loop ou configuração errada)
- As notificações que chegaram no Telegram fazem sentido com o que realmente aconteceu?

10 minutos de revisão semanal previne horas de diagnóstico quando algo quebra há semanas sem que você saiba.

### Revisão mensal do prompt (30 minutos)

Prompts degradam com o tempo — não tecnicamente, mas contextualmente. O mercado muda, seu ICP muda, seu posicionamento muda. Um prompt que estava perfeito há 3 meses pode não refletir mais a realidade do seu negócio.

Uma vez por mês:
- Leia as últimas 10 mensagens geradas pelo agente
- Estão com o tom e conteúdo que você quer?
- Alguma mensagem gerou resposta negativa ou estranha do lead?
- Seu ICP mudou? Seus critérios de qualificação mudaram?

Se necessário, ajuste o prompt. Registre a versão anterior e a data da mudança.

### Rotação de credenciais

Conexões com Google, OpenAI, e outros serviços usam tokens de acesso. Esses tokens expiram e precisam ser renovados. O Make notifica quando uma conexão expira, mas é melhor ser proativo.

A cada 3 meses, verifique as conexões ativas no Make (em "Connections") e renove as que estão próximas de expirar.

### Backup do cenário

O Make não tem "export automático" de cenários no plano gratuito. Para fazer backup:
- Documente cada cenário em um Google Doc com print do canvas + lista dos módulos + texto dos prompts
- Isso garante que você pode reconstruir se precisar mudar de conta ou de ferramenta

---

## Exercício prático

Esta é a entrega final do módulo. Você vai construir e ativar o Assistente de Atendimento e Qualificação completo.

**Critérios de conclusão:**

1. O formulário de aplicação está publicado com pelo menos 6 campos de qualificação
2. O fluxo no Make tem pelo menos 8 módulos conectados, cobrindo entrada, qualificação, roteamento, registro e notificação
3. O prompt de qualificação usa seu ICP real
4. Você executou pelo menos 6 testes com perfis variados (2 HOT, 2 WARM, 2 COLD)
5. A planilha de CRM registra corretamente todos os 6 leads de teste
6. As notificações no Telegram chegaram para todos os 6 testes
7. Você recebeu pelo menos um rascunho de e-mail gerado pela IA com qualidade suficiente para enviar com ajustes mínimos

**Documentação do projeto:**

Prepare um documento de 1 página com:
- Descrição do problema que o agente resolve
- Tempo manual que a tarefa levava antes
- Estrutura do fluxo (lista dos módulos)
- Prints do cenário no Make e do histórico de execuções
- Avaliação da qualidade do output após os 6 testes

Esse documento é o registro do seu primeiro agente produtivo.

---

## Resumo

- Um agente produtivo resolve problema real, opera de forma confiável, e entrega output que você usa com ajustes mínimos
- A arquitetura do Assistente de Atendimento segue o padrão: entrada → histórico → qualificação por IA → roteamento → registro → notificação
- Pedir output em JSON do OpenAI é fundamental — permite que os módulos seguintes extraiam campos de forma confiável
- Ative gradualmente: modo rascunho primeiro, envio automático só depois de calibrar a qualidade
- Meça precisão de qualificação, qualidade das mensagens, tempo economizado, e taxa de erro
- Prompts específicos e concisos produzem outputs mais consistentes que prompts longos e vagos
- Documente tudo: o prompt, a estrutura, as métricas — você vai precisar rever e iterar
- Esse agente é o ponto de partida. Com ele validado, você tem o modelo para construir o próximo
