# Aula 3 — Agentes Multi-Passo: Como Encadear Tarefas

## O que você vai entender nesta aula

Você vai aprender como construir automações que executam múltiplas etapas em sequência, como adicionar lógica condicional que torna o fluxo inteligente, como a memória funciona entre etapas, e como combinar a geração de conteúdo por IA com ações automáticas para criar fluxos que fazem trabalho real.

---

## 1. Por que uma etapa não é suficiente

Na aula anterior, você criou uma automação simples: um gatilho, uma ação. Isso resolve problemas simples. Mas a maioria dos processos reais no trabalho não tem apenas dois passos.

Pense em como você normalmente processa um novo lead:

1. Lead preenche formulário
2. Você verifica se é um lead qualificado (tem o perfil certo?)
3. Se sim: você envia um e-mail personalizado com proposta
4. Você cria uma tarefa no seu sistema de gerenciamento
5. Você adiciona o contato ao seu CRM
6. Se não: você envia um e-mail genérico agradecendo pelo contato

Isso são 6 etapas, com uma condição no meio. Se você fizesse isso manualmente para cada lead, demoraria 10-15 minutos. Se você tiver 20 leads por semana, são 3-5 horas por semana só nessa tarefa.

Uma automação multi-passo resolve isso completamente.

A diferença entre automação simples e automação multi-passo não é de conceito — é de composição. Você está empilhando ações. Cada ação recebe os dados da ação anterior, os processa, e passa o resultado para a próxima.

---

## 2. Como os dados fluem entre etapas

Esse é o conceito mais importante desta aula. Entender fluxo de dados entre etapas é o que separa quem consegue construir automações funcionais de quem fica travado.

Imagine uma linha de montagem. Na primeira estação, entra uma peça bruta. Na segunda estação, ela é moldada. Na terceira, pintada. Na quarta, verificada. O produto final não existe na primeira estação — ele vai sendo construído ao longo do processo.

Automações multi-passo funcionam assim. O output de cada etapa se torna disponível para as etapas seguintes.

**Exemplo concreto:**

- **Etapa 1** (Gatilho): Lead preenche formulário → dados disponíveis: nome, e-mail, cidade, setor
- **Etapa 2** (Ação): Consultar planilha para verificar se a cidade está na lista de cidades atendidas → dado adicionado: resultado (sim/não)
- **Etapa 3** (Condição): SE resultado = "sim" → ir para etapa 4A. SE resultado = "não" → ir para etapa 4B
- **Etapa 4A** (Ação): Enviar e-mail personalizado usando o nome do lead (da etapa 1) e informações da cidade
- **Etapa 4B** (Ação): Adicionar lead a uma lista de "aguardando expansão"

Em toda etapa, você tem acesso a todos os dados produzidos pelas etapas anteriores. No Make, isso aparece como variáveis que você pode clicar e inserir. No Zapier, é a mesma coisa.

---

## 3. Lógica condicional: tornando o fluxo inteligente

Automações sem condições fazem a mesma coisa para todo input. Automações com condições discriminam e agem de forma diferente dependendo da situação.

No Make, condições são chamadas de "filters" (entre módulos) ou "routers" (para criar múltiplos caminhos paralelos).

### Filtros simples

Um filtro verifica uma condição entre duas etapas. Se a condição for verdadeira, o fluxo continua. Se for falsa, o fluxo para ali.

Exemplo: filtro entre "receber e-mail" e "criar tarefa" — condição: o assunto deve conter a palavra "urgente". Só e-mails com "urgente" no assunto criam tarefa.

### Routers (roteadores)

Um router divide o fluxo em múltiplos caminhos. Cada caminho tem sua própria condição e suas próprias ações.

Exemplo: router após verificar o tipo de cliente:
- Caminho A: cliente novo → envia e-mail de boas-vindas + adiciona ao CRM + cria onboarding
- Caminho B: cliente recorrente → envia e-mail de upsell + atualiza perfil no CRM
- Caminho C: cliente inativo → adiciona à campanha de reativação

Todos os três caminhos existem no mesmo fluxo. O router determina qual caminho cada lead vai percorrer.

### Operadores lógicos

Condições podem usar:
- **Igual a / diferente de**: o campo e-mail contém "@empresa.com"
- **Contém / não contém**: o texto da mensagem contém "urgente"
- **Maior que / menor que**: o valor do pedido é maior que R$1.000
- **Existe / não existe**: o campo telefone está preenchido
- **E / OU**: (campo X contém "urgente") E (remetente está na lista de clientes VIP)

---

## 4. Integrando IA generativa no fluxo

Aqui a coisa fica interessante. Você pode incluir um passo de geração de conteúdo por IA no meio do seu fluxo.

O Make tem integração nativa com OpenAI (ChatGPT) e outros LLMs. Zapier também. Isso significa que você pode criar fluxos como:

**Fluxo "Lead recebido → E-mail personalizado gerado por IA → Enviado":**

1. Gatilho: formulário preenchido com nome, empresa, setor, mensagem
2. Ação (OpenAI): gerar um e-mail personalizado baseado nos dados do lead — "Você é especialista em marketing digital. Escreva um e-mail de resposta inicial para o lead [nome], da empresa [empresa], que atua no setor [setor] e disse: [mensagem]. O e-mail deve ser profissional, com 3 parágrafos, e propor uma reunião de 30 minutos."
3. Ação (Gmail): enviar o e-mail gerado para o lead

**Fluxo "Transcrição de reunião → Ata formatada → Enviada para os participantes":**

1. Gatilho: novo arquivo de transcrição aparece no Google Drive
2. Ação (OpenAI): "Você é um assistente de reuniões. Baseado na transcrição a seguir, crie uma ata estruturada com: decisões tomadas, responsáveis, prazos, próximas ações. Transcrição: [conteúdo do arquivo]"
3. Ação (Google Docs): criar um novo documento com a ata formatada
4. Ação (Gmail): enviar o link do documento para os participantes cadastrados

**Fluxo "Avaliação de cliente → Análise de sentimento → Escalada se necessário":**

1. Gatilho: nova avaliação recebida (Typeform ou Google Forms)
2. Ação (OpenAI): "Analise o sentimento desta avaliação e classifique como: POSITIVO, NEUTRO ou NEGATIVO. Retorne apenas uma dessas três palavras. Avaliação: [texto]"
3. Condição: SE resposta = "NEGATIVO"
4. Ação: enviar alerta no Slack para você + criar tarefa de acompanhamento

O que torna isso poderoso: você usa o LLM para as partes que precisam de linguagem e julgamento (escrever o e-mail, analisar sentimento, formatar um documento), e usa as ações de automação para as partes que precisam de execução confiável (enviar e-mail, criar arquivo, adicionar ao CRM).

---

## 5. Memória entre etapas: o que fica, o que some

Existe uma distinção importante que afeta como você constrói fluxos mais complexos.

**Memória dentro de uma execução**: Dentro de um único fluxo em execução, todos os dados de todas as etapas anteriores ficam disponíveis. Se a etapa 1 coletou o nome do lead e a etapa 5 precisa desse nome, ele está lá. Isso é a memória de execução.

**Memória entre execuções**: Quando o fluxo termina e começa de novo para outro lead, os dados da execução anterior são apagados. Cada execução começa do zero. Isso é intencional — evita que dados de um cliente apareçam no processamento de outro.

Para a maioria dos casos, isso não é problema. Mas às vezes você precisa de informações que persistem entre execuções — por exemplo, um contador de quantos leads chegaram hoje, ou o histórico de mensagens de um cliente específico.

A solução é usar uma planilha ou banco de dados como memória externa. A automação lê e escreve nessa planilha conforme necessário, e os dados ficam lá independente de quantas execuções aconteceram.

**Exemplo**: fluxo que conta leads por dia:
1. Lead chega
2. Automação lê o valor atual na célula "Leads Hoje" na planilha
3. Automação soma 1 ao valor
4. Automação escreve o novo valor de volta na planilha
5. Continua processando o lead normalmente

Essa planilha funciona como memória persistente do processo.

---

## 6. Construindo um fluxo real multi-passo no Make

Vamos construir um fluxo completo e útil: **"Lead qualificado → E-mail personalizado gerado por IA → Tarefa criada → Notificação no Telegram".**

Você vai precisar:
- Conta no Make (gratuita)
- Conta Google (Forms + Gmail + Sheets)
- Conta na OpenAI com créditos (você recebe créditos gratuitos ao criar a conta)
- Um bot no Telegram (gratuito, instrução abaixo)

### Por que esse fluxo é valioso

Toda vez que chega um lead qualificado:
- Ele recebe um e-mail personalizado imediatamente (você não pode mais esquecer de responder)
- Você cria automaticamente uma tarefa de acompanhamento
- Você recebe uma notificação no celular para estar ciente

Tudo isso sem você tocar em nada.

### Estrutura do fluxo

**Módulo 1** — Gatilho: Google Forms → Watch Responses

Configure um formulário com: Nome, E-mail, Empresa, Setor, Mensagem

**Módulo 2** — Ação: OpenAI → Create Completion

Conecte sua conta OpenAI. No campo "Prompt":

```
Você é um especialista em marketing digital e vendas consultivas. Escreva um e-mail de resposta inicial para o seguinte lead:

Nome: {{nome do formulário}}
Empresa: {{empresa do formulário}}
Setor: {{setor do formulário}}
Mensagem original: {{mensagem do formulário}}

O e-mail deve:
- Ser personalizado para a realidade do lead
- Ter no máximo 3 parágrafos
- Propor uma conversa de 30 minutos para entender melhor as necessidades
- Ter um tom profissional mas humano
- Terminar com meu nome e "Marketing Estratégico"

Retorne apenas o corpo do e-mail, sem assunto.
```

**Módulo 3** — Ação: Gmail → Send an Email

- Para: {{e-mail do formulário}}
- Assunto: "Re: Sua mensagem - {{nome do formulário}}"
- Corpo: {{output do OpenAI}}

**Módulo 4** — Ação: Google Sheets → Add a Row

Na sua planilha de CRM/leads, adicionar uma linha com:
- Data/hora da execução
- Nome, e-mail, empresa, setor (do formulário)
- Nota: "E-mail enviado automaticamente"

**Módulo 5** — Ação: Telegram → Send a Message

Para criar um bot Telegram gratuito: abra o Telegram, fale com @BotFather, crie um bot novo, copie o token. No Make, conecte usando o token.

Mensagem:
```
Novo lead recebido!
Nome: {{nome}}
Empresa: {{empresa}}
Setor: {{setor}}
E-mail personalizado enviado.
```

### Testando e ativando

1. Clique em "Run once"
2. Preencha o formulário com dados reais (seu próprio e-mail)
3. Verifique se: o e-mail chegou, a planilha foi atualizada, a notificação chegou no Telegram
4. Ajuste o prompt do OpenAI até o e-mail ficar com o tom que você quer
5. Ative o cenário

---

## 7. Tratamento de erros em fluxos multi-passo

Fluxos com muitas etapas têm mais pontos de falha. Uma etapa que falha pode fazer as seguintes nunca executarem. Você precisa antecipar isso.

### Erros comuns e como lidar

**API do OpenAI lenta ou fora do ar**: Configure retry — o Make pode tentar novamente automaticamente algumas vezes antes de desistir. Nas configurações do módulo OpenAI, há opção de retry.

**Dados faltando no formulário**: Se um campo obrigatório veio vazio, as etapas seguintes podem quebrar. Use filtros para verificar que os campos críticos não estão vazios antes de continuar.

**Token do Gmail expirou**: Conexões com Google expiram periodicamente. Quando acontece, o Make notifica por e-mail. Basta reconectar. Para evitar susto, verifique o histórico de execuções semanalmente.

**Cota de tokens da OpenAI esgotada**: A API cobra por token. No plano gratuito inicial, você tem créditos limitados. Configure um alerta quando os créditos estiverem baixos.

### Notificações de erro

Configure o Make para te notificar quando um cenário falha. Em "Settings" do cenário, ative as notificações de erro por e-mail. Assim você sabe imediatamente quando algo quebrou.

---

## 8. Custo de token em fluxos com IA: o que você precisa saber antes de escalar

Quando você integra OpenAI ou outro LLM no seu fluxo, cada chamada tem um custo em tokens. Para um fluxo de teste ou baixo volume, esse custo é insignificante — centavos por dia. Para fluxos que rodam centenas de vezes por dia, pode escalar rapidamente.

Entender como os custos funcionam evita surpresas.

### Como tokens são cobrados

A OpenAI cobra separadamente por tokens de input (o que você manda no prompt) e tokens de output (o que o modelo responde).

Valores aproximados do GPT-4o mini (o modelo mais custo-eficiente para a maioria dos casos práticos):
- Input: ~US$0.15 por 1 milhão de tokens
- Output: ~US$0.60 por 1 milhão de tokens

Para ter uma noção: 1.000 tokens equivalem a aproximadamente 750 palavras em inglês (ou ~600 em português, já que o português geralmente usa mais tokens).

### Estimativa para o fluxo de qualificação de leads

Prompt de sistema + dados do formulário + ICP: aproximadamente 500-800 tokens de input.
Resposta com JSON de qualificação + mensagem personalizada: aproximadamente 400-600 tokens de output.

Custo por execução com GPT-4o mini: ~US$0.001 (0,1 centavo de dólar).

Para 100 leads por mês: US$0.10 (cerca de R$0.58).
Para 1.000 leads por mês: US$1 (cerca de R$5.80).

Esse custo é negligenciável. O GPT-4o mini tem qualidade mais do que suficiente para qualificação de leads e geração de e-mails padrão.

### Quando o custo importa

O custo começa a importar quando:
- Você usa GPT-4o (dez vezes mais caro que o mini) onde o mini resolve
- Seu prompt tem muito contexto desnecessário (texto que não adiciona qualidade)
- Você está processando documentos inteiros quando só precisava de trechos
- O fluxo roda muitas vezes por dia por erro de configuração do gatilho

### Estratégias de controle de custo

**Use o modelo certo para cada etapa**: Classificação simples e geração de e-mails padronizados → GPT-4o mini. Análise de documentos complexos, raciocínio estratégico → GPT-4o ou Claude.

**Mantenha os prompts concisos**: Um prompt de 3.000 tokens custa 5x mais que um de 600 tokens. Se o output é equivalente, o prompt mais curto é melhor.

**Configure limites de gasto**: Na conta OpenAI, defina um limite de gasto mensal. Se você atingir o limite, as chamadas são bloqueadas em vez de continuar gerando custo.

**Monitore o uso**: No dashboard da OpenAI, você pode ver o custo por dia. Acesse regularmente nos primeiros meses de cada fluxo novo.

---

## Erros comuns

### Erro 1: Colocar lógica demais no LLM

Usar o ChatGPT para decidir para qual lista um lead vai, se deve ou não enviar e-mail, qual desconto aplicar — todas dentro de um único prompt. O LLM vai cometer erros de julgamento que você não percebe.

**Mecanismo**: LLMs são bons em linguagem, não em lógica condicional precisa. Para decisões binárias (sim/não, categoria A ou B), use a lógica nativa da ferramenta de automação (filtros e routers), não o LLM.

**Como corrigir**: Use o LLM apenas para o que ele é bom — gerar texto, resumir, classificar sentimento com nuance. Para decisões lógicas precisas, use os filtros da ferramenta de automação.

### Erro 2: Prompt sem contexto suficiente

"Escreva um e-mail de resposta" sem dar nenhuma informação sobre quem você é, qual é o tom, qual é o objetivo. O e-mail vai ser genérico.

**Mecanismo**: O LLM preenche lacunas com o que é mais provável estatisticamente — o que significa um e-mail corporativo genérico.

**Como corrigir**: Dê contexto no prompt: quem você é, qual é o seu posicionamento, qual é o objetivo do e-mail, qual é o tom desejado, exemplos se possível.

### Erro 3: Fluxo sem ponto de revisão humana em ações de alto impacto

Automação que envia e-mails comerciais automaticamente, faz posts em redes sociais de clientes, ou deleta dados — sem revisão humana.

**Mecanismo**: Quando o fluxo tem um erro (dado errado, prompt que gera conteúdo inadequado), o dano já aconteceu antes de você ver.

**Como corrigir**: Para ações de alto impacto, use uma etapa intermediária: em vez de enviar o e-mail diretamente, crie um rascunho no Gmail e te notifique para revisar. Ou poste numa planilha de aprovação antes de publicar.

### Erro 4: Não versionar os prompts

Você testa, funciona, ativa, depois muda o prompt "um pouquinho" sem registrar o que mudou. Daqui a três semanas, o fluxo está gerando outputs piores e você não sabe por quê.

**Mecanismo**: Prompts são código. Mudanças sem versionamento são mudanças sem rastreabilidade.

**Como corrigir**: Mantenha uma planilha simples com versão do prompt, data da mudança, e motivo. Se o output piorar, você pode reverter.

### Erro 5: Construir tudo de uma vez

Montar o fluxo inteiro de 8 etapas de uma vez e tentar fazer funcionar de ponta a ponta.

**Mecanismo**: Quando não funciona, você não sabe qual das 8 etapas falhou.

**Como corrigir**: Construa e teste passo a passo. Etapa 1 funcionando? Adicione a etapa 2. Funciona? Adicione a 3. Assim você localiza exatamente onde está o problema.

---

## Exercício prático

Construa o fluxo completo desta aula:

**"Lead via formulário → E-mail personalizado por IA → Planilha atualizada → Notificação no Telegram"**

Critérios de conclusão:
1. O formulário deve ter pelo menos 4 campos: nome, e-mail, empresa, mensagem
2. O e-mail gerado deve usar pelo menos 2 dados do formulário de forma personalizada
3. A planilha deve registrar cada lead com data/hora
4. A notificação no Telegram deve chegar em menos de 2 minutos após o preenchimento
5. O fluxo deve funcionar em 3 execuções consecutivas sem erro

Documente: tire print do cenário no Make mostrando todos os módulos conectados, e do histórico de execuções mostrando pelo menos 3 execuções bem-sucedidas.

---

## 9. Padrões de design para fluxos multi-passo

À medida que você constrói mais fluxos, vai perceber que certos padrões se repetem. Conhecer esses padrões de antemão te poupa tempo de descoberta.

### Padrão 1: Enriquecimento progressivo

O dado que chega no gatilho é simples (e-mail, nome, empresa). Cada etapa adiciona mais informação a esse dado. Ao chegar na última ação, você tem um perfil completo.

Exemplo: lead chega → busca histórico (adiciona dados de interação anterior) → classifica por IA (adiciona pontuação) → busca informações da empresa em base externa (adiciona dados de mercado) → gera resposta personalizada com tudo isso.

Cada etapa enriquece o objeto de dados que está sendo processado.

### Padrão 2: Fan-out / Fan-in

Um evento dispara múltiplas ações em paralelo. Depois, você consolida os resultados.

Exemplo: novo cliente confirmado → (em paralelo) criar pasta no Drive + adicionar ao CRM + enviar e-mail de boas-vindas + criar projeto no Asana → depois de tudo criado, enviar link de onboarding que referencia todos esses itens.

O Make permite execução paralela de módulos. Use quando as ações são independentes entre si — não precisa de uma para fazer a outra.

### Padrão 3: Pipeline de revisão

Você não quer que certas ações aconteçam automaticamente, mas quer que a preparação seja automática.

Exemplo: fluxo gera proposta, mas em vez de enviar diretamente, cria um rascunho + posta em um canal do Slack ou envia notificação para você revisar + aguarda sua aprovação (via um formulário simples ou botão) + só então envia.

Esse padrão é fundamental para qualquer ação de alto impacto onde a automação prepara mas o humano decide.

### Padrão 4: Loop de verificação

Uma automação que monitora periodicamente uma condição e age quando ela muda.

Exemplo: toda manhã, verificar se as campanhas dos clientes têm CTR abaixo do benchmark. Se sim, criar tarefa de revisão. Se não, nenhuma ação.

O Make executa cenários em intervalos — o gatilho de horário ("Schedule") é a base desse padrão.

### Padrão 5: Consolidação periódica

Ao longo do dia/semana, dados são coletados em uma planilha. Em um momento específico, um fluxo processa todos esses dados acumulados de uma vez.

Exemplo: durante a semana, e-mails de clientes são registrados em uma planilha com suas perguntas. Todo domingo às 18h, um fluxo lê todas as perguntas da semana, identifica os temas recorrentes, e gera um documento com as perguntas mais frequentes para sua FAQ.

Esse padrão evita processar cada item individualmente — você processa em batch quando faz sentido.

---

## Resumo

- Automações multi-passo empilham ações em sequência — o output de uma etapa alimenta a próxima
- Lógica condicional (filtros e routers) torna o fluxo inteligente — diferentes inputs tomam caminhos diferentes
- LLMs se integram ao meio do fluxo para gerar conteúdo personalizado com base nos dados que chegaram
- Memória dentro de uma execução persiste naturalmente; memória entre execuções exige armazenamento externo (planilha, banco de dados)
- Construa e teste passo a passo — nunca monte tudo de uma vez e tente fazer funcionar
- Use o LLM para linguagem e nuance; use a lógica da ferramenta de automação para decisões binárias precisas
- Configure notificações de erro — você precisa saber imediatamente quando um fluxo quebra
