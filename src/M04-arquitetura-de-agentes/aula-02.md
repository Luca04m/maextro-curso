# Aula 2 — Automações Simples: Seus Primeiros Fluxos sem Código

## O que você vai entender nesta aula

Você vai aprender o que é uma automação no sentido técnico, como construir seu primeiro fluxo funcional usando Make ou Zapier (planos gratuitos), e entender os três componentes universais que existem em qualquer automação — por que cada um importa e o que quebra quando um deles está errado.

---

## 1. Automação não é complicado — é lógica de "se isso, então aquilo"

Antes de abrir qualquer ferramenta, você precisa entender o mecanismo. Toda automação, por mais complexa que pareça, é variação de uma estrutura simples:

**Quando [evento acontece], faça [ação].**

Isso é tudo.

- Quando um formulário é preenchido → envie um e-mail de boas-vindas
- Quando um e-mail com assunto "Orçamento" chega → crie uma tarefa no Asana
- Quando uma planilha recebe uma nova linha → adicione o contato no CRM
- Quando um post é publicado no Instagram → poste automaticamente no Facebook

Cada um desses é uma automação completa e funcional. Simples assim.

O que muda com automações mais avançadas não é a lógica fundamental — é a quantidade de etapas, as condições que determinam quando cada ação acontece, e as ferramentas conectadas.

Mas o princípio não muda. Você precisa internalizar isso porque vai te libertar do bloqueio mental de achar que automação é coisa de programador.

---

## 2. Os três componentes de qualquer automação

Toda automação — no Make, no Zapier, no n8n, ou em qualquer outra ferramenta — tem três componentes obrigatórios:

### Gatilho (Trigger)

O gatilho é o evento que inicia a automação. Ele responde à pergunta: *O que precisa acontecer para que essa automação rode?*

Exemplos de gatilhos:
- Um e-mail chega na sua caixa de entrada
- Um novo lead preenche um formulário
- Uma hora específica do dia/semana chegou
- Um arquivo é adicionado a uma pasta no Google Drive
- Uma mensagem específica é postada em um canal do Slack
- Um novo pedido chega no e-commerce

**O gatilho é o ponto de entrada.** Sem ele, a automação nunca começa. Um gatilho mal configurado é a causa número um de automações que "não funcionam" — na verdade, elas nunca chegam a ser acionadas.

### Ação (Action)

A ação é o que a automação executa quando o gatilho dispara. Ela responde à pergunta: *O que deve acontecer como resultado?*

Exemplos de ações:
- Enviar um e-mail
- Criar um documento no Google Docs
- Adicionar uma linha em uma planilha
- Fazer um post no Instagram
- Criar uma tarefa no Asana ou Trello
- Enviar uma mensagem no WhatsApp (via API)
- Adicionar um contato ao Mailchimp
- Notificar via Slack ou Telegram

Uma automação pode ter múltiplas ações encadeadas — o gatilho dispara, e então ação 1 ocorre, depois ação 2, depois ação 3. Você vai aprender isso em detalhes na Aula 3.

### Lógica/Filtro (opcional, mas poderoso)

Entre o gatilho e a ação, você pode colocar condições: "execute a ação apenas se [condição for verdadeira]."

Exemplo: "Quando um e-mail chega → SE o remetente estiver na lista de clientes ativos → crie uma tarefa. SENÃO → arquive o e-mail."

Filtros são o que separa automações ingênuas de automações inteligentes. Sem filtros, a automação dispara para tudo. Com filtros certos, ela discrimina e age apenas quando faz sentido.

---

## 3. Make vs Zapier: o que são e qual usar

Existem dezenas de ferramentas de automação no mercado. Para quem está começando no Brasil, sem gastar nada, as duas principais são Make e Zapier.

### Zapier

**O que é**: A ferramenta de automação mais popular do mundo. Interface simples, suporte para mais de 7.000 aplicativos. Pensada para não-técnicos.

**Plano gratuito**: 100 tarefas por mês (uma "tarefa" é cada vez que uma ação é executada), automações de 2 etapas (um gatilho + uma ação), sem filtros avançados, sem loops.

**Ponto forte**: Facilidade extrema. Você consegue criar sua primeira automação em menos de 10 minutos. Interface muito clara, ótima documentação.

**Ponto fraco**: O plano gratuito é bem limitado. Automações de 3 etapas ou mais já exigem plano pago (a partir de ~$20/mês). Para quem está só testando, funciona. Para quem quer usar como ferramenta de trabalho real, o limite aparece rápido.

**Quando usar**: Testes iniciais, automações simples de 2 passos, quando você precisa de algo funcionando em minutos.

### Make (antigo Integromat)

**O que é**: Plataforma de automação mais poderosa visualmente. Interface de fluxo visual onde você literalmente arrasta e conecta módulos como blocos. Suporta mais de 1.000 apps, loops, condições, transformações de dados.

**Plano gratuito**: 1.000 operações por mês, automações de múltiplas etapas ilimitadas, filtros e condicionais incluídos. Bem mais generoso que o Zapier.

**Ponto forte**: Muito mais poderoso no plano gratuito. Você pode criar fluxos complexos com condicionais e múltiplas etapas sem pagar. A interface visual é intuitiva assim que você entende o conceito.

**Ponto fraco**: Curva de aprendizado ligeiramente maior que o Zapier. A interface visual pode ser confusa no início — mas você aprende em horas, não semanas.

**Quando usar**: Fluxos com mais de 2 etapas, quando você precisa de condicionais, quando o volume do Zapier gratuito não é suficiente. É a escolha para uso real.

**Recomendação direta**: Para aprender, use Zapier para sentir o básico. Para trabalho real, mude para Make. O plano gratuito do Make é suficiente para a maioria dos cenários de um profissional solo por meses.

---

## 4. Criando sua primeira automação no Make — passo a passo

Vamos criar uma automação real: **"Quando receber um e-mail com um assunto específico, criar automaticamente uma tarefa no Google Tasks."**

Isso resolve um problema real: você recebe vários e-mails de clientes pedindo pequenas ações. Em vez de ficar copiando manualmente para sua lista de tarefas, a automação faz isso.

### Passo 1: Criar conta no Make

Acesse make.com, crie conta gratuita. Não precisa cartão de crédito.

### Passo 2: Criar novo cenário

No painel, clique em "Create a new scenario". Você vai ver uma tela branca com um círculo com um sinal de +. Esse é o seu canvas — onde você vai montar o fluxo.

### Passo 3: Configurar o gatilho (Gmail)

Clique no círculo de +. Pesquise por "Gmail". Selecione o módulo "Watch Emails" (monitorar e-mails). Conecte sua conta Google (o Make vai pedir permissão para acessar o Gmail — autorize). Configure:
- Folder: Inbox
- Criteria: No filter (ou "From" se quiser filtrar por remetente)
- Maximum number of emails: 1

### Passo 4: Adicionar um filtro (opcional mas recomendado)

Clique no ícone de "wrench" (chave) entre os módulos para adicionar um filtro. Configure: "Subject" "Contains" "Orçamento" (ou a palavra que você quer rastrear). Isso faz com que a automação só rode quando o assunto contiver essa palavra.

### Passo 5: Adicionar a ação (Google Tasks)

Clique no + depois do filtro. Pesquise "Google Tasks". Selecione "Create a task". Conecte a conta Google. Configure:
- Task list: "Clientes" (ou a lista que você usar)
- Title: use a variável dinâmica — clique no campo, selecione "Subject" do e-mail
- Notes: pode adicionar o corpo do e-mail ou o nome do remetente

### Passo 6: Testar

Clique em "Run once" para testar. Mande um e-mail para si mesmo com o assunto que você configurou. Veja o cenário executar e a tarefa aparecer no Google Tasks.

### Passo 7: Ativar

Se funcionou, clique no toggle para ativar o cenário. Agora ele roda automaticamente em segundo plano.

**Parabéns.** Você acabou de criar sua primeira automação funcional.

---

## 5. Conceitos técnicos que você precisa saber

Algumas coisas vão aparecer em qualquer ferramenta de automação. Vale entender agora:

### Variáveis dinâmicas

Quando você configura uma ação, pode usar dados que vieram do gatilho. Por exemplo, no campo "Título da tarefa" você pode colocar o assunto do e-mail, o nome do remetente, ou qualquer dado que o e-mail continha. Isso torna a automação dinâmica — ela não cria a mesma tarefa toda vez, ela cria a tarefa certa com os dados daquele e-mail específico.

### Polling vs Webhooks

Existem dois tipos de gatilho:

**Polling**: a ferramenta "fica perguntando" para o serviço em intervalos regulares — "chegou alguma coisa nova?" No plano gratuito do Make, isso acontece a cada 15 minutos. Para e-mails não urgentes, funciona. Para resposta imediata, não serve.

**Webhooks**: o serviço avisa a ferramenta em tempo real quando algo acontece. É instantâneo. Nem todos os aplicativos suportam webhooks, mas quando suportam, a resposta é imediata.

Para a maioria dos casos de uso de um profissional solo, polling de 15 minutos já é suficiente.

### Mapeamento de dados

Quando você conecta dois apps, você precisa dizer para a ferramenta "qual campo do app A corresponde a qual campo do app B". O nome do lead que chegou no formulário vai para qual campo do CRM? O assunto do e-mail vai para o título da tarefa ou para a descrição? Esse processo é chamado de mapeamento — e é onde acontecem a maioria dos erros de configuração.

---

## 6. Cinco automações simples para começar hoje

Essas cinco automações são as mais úteis para profissionais solos, todas possíveis no plano gratuito do Make ou Zapier:

### Automação 1: E-mail → Tarefa

**Gatilho**: Novo e-mail no Gmail com palavra-chave no assunto
**Ação**: Criar tarefa no Google Tasks / Notion / Trello
**Por que é útil**: Converte e-mails de clientes em tarefas sem esforço manual

### Automação 2: Formulário → Planilha + E-mail

**Gatilho**: Novo preenchimento no Google Forms ou Typeform
**Ação 1**: Adicionar linha na planilha de leads
**Ação 2**: Enviar e-mail de confirmação para o lead
**Por que é útil**: Captura automaticamente todos os contatos que chegam sem depender de você ver o formulário

### Automação 3: Post único → Múltiplas redes sociais

**Gatilho**: Novo item em uma planilha (ou novo post aprovado no buffer)
**Ação**: Postar no Instagram + Facebook + LinkedIn
**Por que é útil**: Você escreve uma vez, aparece em todos os lugares

### Automação 4: Agendamento → Lembrete

**Gatilho**: Novo evento criado no Google Agenda com tag específica
**Ação**: Enviar WhatsApp/SMS/Telegram 24h antes e 1h antes
**Por que é útil**: Elimina clientes que faltam em reunião por esquecimento

### Automação 5: Relatório semanal automático

**Gatilho**: Todo domingo às 18h (gatilho de horário)
**Ação**: Ler dados de uma planilha, compilar em um documento Google Docs
**Por que é útil**: Você sempre tem um resumo da semana sem precisar compilar manualmente

---

## 7. O que acontece quando uma automação falha: diagnóstico rápido

Automações falham. Isso é normal e esperado. O problema não é a falha em si — é não saber o que fazer quando ela acontece.

O Make tem um histórico de execuções detalhado. Cada execução mostra:
- Status: sucesso, aviso, ou erro
- Qual módulo falhou
- A mensagem de erro exata
- Os dados que estavam sendo processados quando a falha ocorreu

Quando você vê um erro, o processo de diagnóstico tem quatro perguntas:

**Pergunta 1: Qual módulo falhou?**
O Make aponta exatamente o módulo com problema. Se foi o módulo do Google Sheets, o problema está na conexão com o Google ou no mapeamento das colunas. Se foi o módulo Gmail, provavelmente é permissão ou token expirado. Se foi o módulo OpenAI, pode ser cota esgotada, timeout, ou o formato do output.

**Pergunta 2: Esse erro é de conexão ou de dados?**
Erros de conexão (token expirado, autenticação inválida) se resolvem reconectando o app. Erros de dados (campo vazio que era obrigatório, formato inesperado) se resolvem adicionando validação ou tratamento de exceção.

**Pergunta 3: É um erro pontual ou consistente?**
Se uma execução falhou mas as 10 anteriores foram bem, provavelmente foi um dado atípico naquela execução específica. Se 3 execuções seguidas falharam no mesmo módulo, há um problema sistemático que precisa de correção.

**Pergunta 4: O dado que causou o erro pode aparecer de novo?**
Se um campo de formulário pode chegar vazio, e seu fluxo assume que ele sempre estará preenchido, você tem um bug estrutural. Adicione um filtro antes do módulo que depende desse campo: "Se [campo] não estiver preenchido, notificar em vez de continuar."

### Erros frequentes e como resolver

**"Error 403: Insufficient permissions" (Google)**
Reconecte a integração Google no Make. Às vezes é necessário revogar o acesso e autorizar novamente.

**"Error 429: Rate limit exceeded" (OpenAI)**
Você chamou a API muitas vezes em pouco tempo. Configure um intervalo entre execuções ou use um modelo diferente. Para planos gratuitos da OpenAI, o limite é baixo.

**"Invalid JSON" (módulo JSON Parse)**
O OpenAI retornou algo que não é JSON válido. Adicione no prompt a instrução de retornar apenas JSON puro. Ou use o módulo Text Parser do Make para extrair o JSON da resposta antes de parsear.

**"No results found" (Google Sheets Search)**
O dado que você buscou não existe na planilha. Isso pode ser esperado (contato novo) ou um erro de mapeamento (você está buscando o campo errado). Adicione uma condição após a busca para tratar o caso de "nenhum resultado encontrado".

---

## Erros comuns

### Erro 1: Criar automação antes de mapear o processo manualmente

Você não sabe como automatizar algo que você não entendeu manualmente. Se o processo manual tem ambiguidades, a automação vai amplificar essas ambiguidades.

**Mecanismo**: Automação não resolve problemas de processo — ela os acelera. Se o processo manual é confuso (quando exatamente devo criar uma tarefa? que informação é necessária?), a automação vai criar confusão na velocidade da máquina.

**Como corrigir**: Antes de automatizar, descreva o processo manual em passos claros: "Quando X acontece, eu faço Y, verificando Z." Se você não consegue descrever assim, o processo ainda não está pronto para automação.

### Erro 2: Não testar com dados reais antes de ativar

Testar com dados fictícios é diferente de testar com dados reais. E-mails de verdade têm formatações inesperadas. Formulários reais às vezes enviam campos vazios.

**Mecanismo**: Dados de teste são limpos e perfeitos. Dados reais são bagunçados.

**Como corrigir**: Antes de ativar, envie para si mesmo e-mails reais que imitam os que clientes mandam. Preencha o formulário como um cliente preencheria, incluindo casos como "deixar campo em branco" ou "colocar informação no campo errado".

### Erro 3: Esquecer de monitorar nos primeiros dias

Você ativa, vai embora. Na semana seguinte, descobre que a automação estava falhando silenciosamente há dias.

**Mecanismo**: Automações falham por razões variadas — mudança de API, permissão expirada, formato de dado diferente do esperado. Sem monitoramento, você não sabe que falhou.

**Como corrigir**: Nos primeiros 7 dias após ativar uma automação, verifique o histórico de execuções diariamente. Depois de estável, reduz para semanal.

### Erro 4: Conectar a ferramenta errada para o caso de uso

Usar Zapier quando você precisa de condicionais e múltiplas etapas no plano gratuito — você vai bater no limite e ficar frustrado.

**Mecanismo**: Cada ferramenta tem seus pontos fortes. Zapier é simples mas limitado. Make é poderoso mas tem uma curva. Escolha baseada no que você precisa, não no que é mais fácil de começar.

**Como corrigir**: Leia os planos gratuitos antes de começar. Se você vai precisar de mais de 2 etapas, vá direto para o Make.

### Erro 5: Automatizar tarefas que exigem julgamento contextual

"Responder qualquer e-mail de cliente automaticamente com a mensagem X" pode funcionar para e-mails de confirmação simples. Mas para e-mails de reclamação ou situações delicadas, a resposta automática pode piorar o problema.

**Mecanismo**: Automações são determinísticas nas ações — elas fazem o que você configurou, sem contexto adicional. Um e-mail de cliente furioso não deve receber a mesma resposta automática padrão de uma confirmação de reunião.

**Como corrigir**: Para e-mails de alto contexto, use a automação para *preparar* uma resposta para você revisar, não para enviar automaticamente.

---

## Exercício prático

Você vai criar sua primeira automação funcionando hoje.

**Tarefa**: Criar a automação "Formulário → Planilha + Notificação"

**Passo 1**: Crie um formulário simples no Google Forms com 3 campos:
- Nome
- E-mail
- Mensagem

**Passo 2**: Crie uma conta no Make (make.com, gratuito).

**Passo 3**: Crie um novo cenário com:
- Gatilho: Google Forms → "Watch Responses" (conectar sua conta Google)
- Ação 1: Google Sheets → "Add a Row" (criar uma planilha chamada "Leads" e mapear os campos)
- Ação 2: Gmail → "Send an Email" (enviar um e-mail para você mesmo com as informações do lead)

**Passo 4**: Teste preenchendo o formulário uma vez. Verifique se a planilha foi atualizada e se o e-mail chegou.

**Passo 5**: Se funcionou, ative o cenário.

**Entregável**: Você deve ter um cenário ativo no Make, com o histórico mostrando pelo menos uma execução bem-sucedida. Tire um print da tela do cenário e do histórico de execuções — isso é sua prova de entrega.

---

## 8. Como documentar suas automações para não perder o fio

Automações invisíveis são automações que você esquece. Quando algo quebra depois de 3 meses, você não lembra exatamente o que o fluxo faz, por que foi configurado assim, ou quais apps dependem dele.

A solução é simples e leva 5 minutos por automação: uma planilha de documentação.

### O que documentar

Crie uma planilha com uma linha por automação. Colunas obrigatórias:

**Nome do fluxo**: algo descritivo. "Form → CRM + Email" é melhor que "Cenário 3".

**O que faz**: uma frase. "Quando formulário de contato é preenchido, adiciona à planilha de leads e envia e-mail de confirmação para o contato."

**Gatilho**: qual evento inicia o fluxo.

**Apps conectados**: lista de todos os apps que o fluxo usa. Útil quando você troca de conta de algum serviço e precisa saber quais fluxos precisam ser atualizados.

**Data de criação e última modificação**.

**Status**: Ativo / Pausado / Em manutenção.

**Notas de manutenção**: qualquer coisa que você ajustou, problemas que apareceram, mudanças que fez.

### Por que isso importa mais do que parece

Quando você tem 10 fluxos rodando, você não vai lembrar de todos. Quando você muda de plano no Make ou migra de ferramenta, essa documentação é o que te permite reconstruir rapidamente. Quando você contratar alguém para ajudar com operações, essa documentação é o onboarding deles.

A disciplina de documentar no dia que você cria a automação é muito menor do que o esforço de reconstruir o conhecimento depois.

---

## Resumo

- Toda automação tem três componentes: gatilho (o quê inicia), ação (o quê acontece), lógica/filtro (quando acontece)
- Make é mais poderoso no plano gratuito que o Zapier — múltiplas etapas e filtros incluídos
- Zapier é mais fácil para o primeiro contato, mas você vai migrar para o Make rapidamente
- Os conceitos fundamentais que aparecem em toda ferramenta: variáveis dinâmicas, polling vs webhooks, mapeamento de dados
- As automações mais úteis para início: e-mail→tarefa, formulário→planilha+e-mail, post único→múltiplas redes, agendamento→lembrete
- Antes de automatizar, mapeie o processo manual — automação de processo confuso cria confusão mais rápida
- Monitore os primeiros 7 dias de toda automação nova
- Documente cada automação ao criá-la: nome, o que faz, gatilho, apps, status — 5 minutos agora economiza horas depois
