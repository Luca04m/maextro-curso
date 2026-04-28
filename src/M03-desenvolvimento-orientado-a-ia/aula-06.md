# Aula 6 — Manutenção e Ajustes sem Programador: Como Iterar com IA

## O que você vai entender nesta aula

Você vai aprender como fazer atualizações em projetos existentes usando IA, como organizar o trabalho de manutenção para que seja eficiente, como comunicar mudanças para clientes, e como evitar os problemas mais comuns que surgem quando um site precisa ser atualizado meses depois da criação.

---

## A fase que ninguém planeja: manutenção

Quando você cria um site para um cliente (ou para você mesmo), o trabalho não termina no dia do deploy. Sites precisam de manutenção. Textos mudam. Preços mudam. Horários mudam. O cliente quer adicionar um serviço novo. Uma foto precisa ser trocada. Um botão parou de funcionar depois de uma atualização.

Para a maioria das pessoas que criaram o site sem saber programar, esse momento é um problema: você depende da mesma ferramenta que usou para criar o site, mas não tem certeza de como fazer mudanças sem quebrar o que está funcionando.

Com as ferramentas certas e o processo correto, manutenção é tão simples quanto criar. Às vezes mais simples — porque você já tem a estrutura definida e está apenas ajustando.

---

## Os três tipos de manutenção

Nem toda atualização é igual. Entender o tipo de mudança que você precisa fazer determina a abordagem.

### Tipo 1 — Mudanças de conteúdo

São as mais frequentes e as mais simples: trocar um texto, atualizar um preço, mudar um número de telefone, adicionar um novo depoimento, atualizar uma data de promoção.

Para essas mudanças, você tem duas opções:

**Opção A — Editar diretamente no código:** Se você usou Cursor ou tem acesso aos arquivos, pode localizar o texto e editar diretamente. Não precisa da IA para isso.

**Opção B — Pedir para a IA alterar:** "No arquivo index.html, localize o texto 'R$ 150,00 por consulta' e substitua por 'R$ 180,00 por consulta'. Mantenha tudo o mais igual."

### Tipo 2 — Mudanças de design

Ajustes visuais que não alteram o conteúdo: mudar a cor de um botão, aumentar o tamanho de uma fonte, reorganizar a ordem das seções, adicionar um espaçamento.

Para essas mudanças, a IA é muito eficiente quando o pedido é específico:

"Mude a cor de todos os botões de CTA de azul (#2563EB) para verde (#16A34A)."

"A seção de depoimentos está muito próxima da seção anterior. Adicione 80px de margem superior na seção de depoimentos."

### Tipo 3 — Novas funcionalidades

Adicionar algo que não existia antes: um novo formulário, uma calculadora, uma galeria de fotos, um botão de WhatsApp que não estava lá, integração com Instagram.

Esse tipo de mudança é o mais complexo e é aqui que o processo precisa ser mais cuidadoso.

---

## O problema da memória: por que IA "esquece" seu projeto

Aqui está algo importante que você precisa entender sobre como as ferramentas de IA funcionam.

A IA não tem "memória permanente" do seu projeto. Cada sessão começa do zero. Quando você abre o Lovable depois de um mês e quer fazer uma mudança, a ferramenta não lembra de nada sobre o projeto — nem das decisões que você tomou, nem dos problemas que resolveu, nem do contexto do cliente.

Isso tem duas implicações práticas:

**Implicação 1:** Você precisa fornecer contexto toda vez que começa uma nova sessão de trabalho em um projeto existente.

**Implicação 2:** Se o código do projeto não está acessível para a ferramenta, você não consegue fazer mudanças — você teria que recriar do zero.

A solução para ambos os problemas é a mesma: manter o código do projeto em um repositório Git (GitHub). Isso garante que a ferramenta sempre tenha acesso ao código atual, e que você possa trabalhar em novas sessões conectando a ferramenta ao repositório.

---

## Como manter projetos atualizáveis

### Para projetos criados no Lovable

O Lovable tem historico de versões integrado. Cada mudança que você faz cria uma versão que pode ser restaurada. Além disso, você pode conectar o projeto ao GitHub:

1. No projeto do Lovable, clique no ícone de configurações
2. Encontre a opção "GitHub Integration"
3. Conecte com sua conta do GitHub
4. Selecione "Create a new repository" ou conecte a um existente
5. O Lovable vai sincronizar automaticamente cada mudança com o repositório

Com isso, você tem um backup permanente e pode trabalhar no projeto de qualquer dispositivo.

### Para projetos criados no Cursor

O Cursor trabalha diretamente com arquivos na sua máquina. Para manter o projeto atualizável:

1. Inicialize o Git na pasta do projeto: `git init`
2. Crie um repositório no GitHub
3. Faça o primeiro commit e push
4. A partir daí, após cada sessão de trabalho, commit e push das mudanças

Isso pode parecer técnico, mas existem formas de fazer sem terminal: o Cursor tem integração com Git nativa (botão de Source Control na barra lateral), e o GitHub Desktop (aplicativo gratuito) torna o processo completamente visual.

---

## O arquivo de contexto: sua memória externa

Aqui está uma prática que faz enorme diferença na manutenção de projetos:

Crie um arquivo de texto (`contexto-projeto.md`) dentro de cada projeto com as seguintes informações:

```
# Projeto: [Nome do Projeto]

## Cliente
Nome: [nome do cliente]
Contato: [WhatsApp/email]

## Descrição do projeto
[O que é este projeto e para que serve]

## Público-alvo
[Quem usa este site e o que espera dele]

## Decisões de design
- Paleta de cores: [cores exatas usadas]
- Fontes: [fontes usadas]
- Tom de comunicação: [formal/informal/técnico/etc.]
- Estilo visual: [referências ou descrição]

## Estrutura da página
[Lista das seções em ordem]

## Elementos funcionais
[Formulários, botões especiais, integrações]

## Histórico de mudanças
- [data] — [descrição da mudança]
- [data] — [descrição da mudança]

## Notas importantes
[Qualquer informação que você precisaria saber antes de mexer neste projeto]
```

Quando você voltar ao projeto semanas depois, você lê esse arquivo antes de qualquer outra coisa. Ele reconstrói o contexto em 2 minutos. Você pode também compartilhar esse contexto com a IA no início de cada sessão.

Como usar o contexto com IA:

"Vou compartilhar o contexto deste projeto antes de pedir qualquer mudança. [Cole o arquivo de contexto]. Agora: preciso adicionar uma seção de FAQ com 5 perguntas no final da página, antes do footer."

---

## Processo para fazer mudanças em projetos existentes

Quando um cliente pede uma mudança, siga este processo:

### 1. Documente o pedido com precisão

Não aceite pedidos vagos. "Quero atualizar o site" não é acionável. Transforme em:

"Você quer: (a) trocar a foto de perfil, (b) atualizar os preços na seção de planos, e (c) adicionar um link para o Instagram no footer. É isso?"

Ter clareza sobre o escopo evita retrabalho.

### 2. Estime o impacto

Mudanças de conteúdo simples: 15-30 minutos de trabalho.
Mudanças de design: 30 minutos a 2 horas dependendo da complexidade.
Novas funcionalidades: 1-4 horas.

Essa estimativa determina quanto você vai cobrar (se estiver cobrando) e quando você pode entregar.

### 3. Faça backup antes de qualquer mudança significativa

Se o projeto está no GitHub: verifique que o estado atual está commitado antes de fazer mudanças grandes.

Se o projeto está no Lovable: tire nota da última versão funcional no histórico.

Se você tem apenas os arquivos no computador: faça uma cópia da pasta antes de qualquer mudança.

### 4. Execute as mudanças em sessão dedicada

Não faça manutenção no meio de outras tarefas. Reserve um bloco de tempo específico para o projeto. Você vai precisar de contexto mental sobre o projeto — fragmentar a atenção aumenta o risco de erro.

### 5. Teste como usuário final

Depois de qualquer mudança, visite o site como se fosse um visitante pela primeira vez. Teste em mobile. Verifique os elementos que você tocou e os adjacentes (mudanças às vezes afetam elementos vizinhos).

### 6. Deploy e confirmação

Após testar, faça o deploy da versão atualizada. Envie um link para o cliente com uma breve descrição do que foi alterado.

---

## Como cobrar por manutenção

Se você está prestando serviço para clientes, a manutenção é uma fonte de renda recorrente. Existem dois modelos:

**Modelo por hora:** Você cobra um valor por hora de trabalho. Bom quando as demandas são imprevisíveis. Desvantagem: o cliente pode sentir que está sendo cobrado por cada mensagem.

**Modelo de retainer (mensalidade):** O cliente paga um valor fixo por mês por um número determinado de horas ou mudanças. Exemplo: "R$ 200/mês por até 4 horas de ajustes." Bom para estabilidade de renda. Funciona melhor quando o cliente tem mudanças frequentes.

**O que incluir em um pacote de manutenção:**
- Até X horas de alterações por mês
- Atualização de textos e imagens
- Correção de bugs
- Backup mensal do projeto
- Resposta em até X horas úteis

O que NÃO deve estar no pacote básico (deve ser cobrado à parte):
- Redesign completo
- Novas páginas
- Novas integrações (banco de dados, pagamentos)
- Migração de plataforma

---

## Manutenção preventiva: o que fazer mesmo sem pedido do cliente

Além de responder a pedidos do cliente, existe manutenção preventiva que você pode fazer proativamente. Isso demonstra profissionalismo e justifica a mensalidade.

**Verificação mensal de funcionamento:**
- O site está carregando?
- Todos os links estão funcionando?
- Formulários ainda enviam?
- O site está acessível no mobile?

**Atualização de conteúdo quando relevante:**
- Datas de promoções venceram? Remova-as.
- Horários de funcionamento mudaram sazonalmente? Atualize.
- O cliente ganhou um prêmio ou certificação? Adicione à seção de credenciais.

**Verificação de velocidade:**
- Use PageSpeed Insights (pagespeed.web.dev) mensalmente
- Se a nota caiu, investigue o motivo

---

## Como iterar um projeto para melhorar resultados

Além de manutenção, existe a iteração estratégica — melhorar o site para melhorar os resultados de negócio do cliente.

Isso requer dados. Você precisa saber o que está funcionando e o que não está. A ferramenta mais simples e gratuita para isso é Google Analytics ou, para versões mais simples, a análise básica que plataformas como Vercel e Netlify oferecem.

Com dados, você pode identificar:

**Alta taxa de abandono no início da página:** As pessoas chegam e saem sem rolar. Isso indica que o hero não está comunicando a proposta de valor com clareza suficiente.

**Cliques no CTA mas sem conversão:** As pessoas clicam no botão mas não completam a ação. Isso pode indicar problema no passo seguinte (o WhatsApp não abre, o formulário tem erro).

**Tráfego mobile alto mas conversão baixa:** A versão mobile pode ter algum problema que não está óbvio no desktop.

Com esses insights, você volta para a IA com pedidos específicos de melhoria — baseados em dados, não em achismos.

---

## Erros comuns

**Erro 1: Fazer mudanças sem backup.**
O mecanismo: mudanças que "parecem simples" podem ter efeitos cascata. Um elemento de CSS alterado pode quebrar o layout em mobile sem que você perceba no desktop. Sempre tenha uma forma de voltar.

**Erro 2: Aceitar pedidos de mudança por mensagem de voz ou de forma verbal.**
O mecanismo: "troca a foto" pode significar dez coisas diferentes para cliente e prestador. Sempre confirme por escrito o escopo exato da mudança antes de executar.

**Erro 3: Fazer múltiplas mudanças em uma única sessão sem testar entre elas.**
O mecanismo: se você fizer 5 mudanças e depois descobrir que algo está errado, não vai saber qual mudança causou o problema. Faça uma mudança, teste, depois avance para a próxima.

**Erro 4: Não comunicar o que foi feito após a manutenção.**
O mecanismo: o cliente não vê o trabalho que você fez. Comunicar o que foi alterado justifica o valor cobrado e demonstra profissionalismo. "Atualizei os preços na seção de planos, adicionei o link do Instagram no footer e corrigi o formulário de contato que estava com erro no campo de telefone."

**Erro 5: Recusar-se a aprender o mínimo de como o código está organizado.**
O mecanismo: você não precisa ser programador, mas entender que um arquivo HTML tem seções com IDs e classes, e que você pode encontrar o texto que quer alterar usando Ctrl+F, vai economizar horas de trabalho ao longo do tempo.

---

## Exercício prático

Escolha o projeto que você criou nas aulas anteriores e simule um processo de manutenção:

1. **Crie o arquivo de contexto** (`contexto-projeto.md`) com todas as informações sobre o projeto
2. **Faça três mudanças simples:**
   - Troque o texto de um botão de CTA
   - Mude a cor de fundo de uma seção
   - Adicione uma nova linha em uma seção existente (um novo serviço, um novo depoimento)
3. Para cada mudança, escreva o prompt específico antes de enviá-lo
4. Depois de cada mudança, teste se funcionou antes de partir para a próxima
5. Ao final, verifique que o site ainda funciona corretamente no mobile

Este exercício treina o fluxo de manutenção. Quando você precisar fazer isso para um cliente real, vai ser familiar.

---

## Resumo

- Manutenção é inevitável e deve ser planejada — não é exceção, é parte do trabalho
- Existem três tipos de mudança: conteúdo (simples), design (médio), novas funcionalidades (complexo)
- A IA não tem memória permanente do seu projeto — você precisa de um repositório GitHub e um arquivo de contexto para manutenção eficiente
- O processo correto de mudança: documentar o pedido com precisão, estimar impacto, fazer backup, executar em sessão dedicada, testar, fazer deploy
- Prompts de manutenção precisam ser cirúrgicos — especifique o que muda e deixe explícito o que não deve mudar
- Manutenção pode ser cobrada como mensalidade (retainer) — é uma fonte de renda recorrente e estável
- Iteração estratégica baseada em dados (taxa de abandono, cliques, conversão) é diferente de manutenção — é melhoria contínua do resultado de negócio
- Comunicar o que foi feito após cada sessão de manutenção é profissionalismo e justifica o valor cobrado
