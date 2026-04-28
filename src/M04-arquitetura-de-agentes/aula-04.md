# Aula 4 — Ferramentas de Automação: Make, n8n e o que Usar no Brasil

## O que você vai entender nesta aula

Você vai entender as diferenças reais entre as três principais ferramentas de automação disponíveis no Brasil — Make, Zapier e n8n —, quais são os planos gratuitos de cada uma, como escolher a ferramenta certa para o seu caso de uso, e o que considerar no contexto brasileiro (custo em reais, suporte em português, integrações relevantes).

---

## 1. Por que a escolha da ferramenta importa

Você pode construir automações incríveis em qualquer uma das ferramentas principais. A diferença não é "qual ferramenta faz mais coisas" — é "qual é o custo, a complexidade e os limites que você vai encontrar na sua situação específica."

Escolher a ferramenta errada cria problemas reais:
- Você aprende em uma plataforma, chega num limite e precisa recomeçar em outra
- Você gasta dinheiro em plano pago quando o gratuito de outra ferramenta já resolveria
- Você monta fluxos complexos em uma ferramenta que cobra por operação, sem perceber que o custo vai escalar

A boa notícia: você não precisa escolher uma única ferramenta para sempre. Muitos profissionais usam Make para automações centrais e Zapier para integrações específicas que só existem lá. O importante é entender o que cada uma oferece.

---

## 2. Zapier — A mais conhecida

### O que é

Zapier é a ferramenta de automação mais popular do mundo, com suporte para mais de 7.000 aplicativos. É a escolha mais fácil para começar: interface limpa, documentação extensa, muitos tutoriais em português na internet.

### Plano gratuito (2025)

- 100 tarefas por mês (uma "tarefa" = uma ação executada)
- Zaps de 2 etapas: um gatilho + uma ação
- Sem filtros condicionais no plano gratuito
- Sem paths (routers) no plano gratuito
- Polling a cada 15 minutos
- 5 Zaps ativos simultaneamente

### Plano pago

- Starter: ~$20/mês (750 tarefas, Zaps de 3 etapas, filtros básicos)
- Professional: ~$50/mês (2.000 tarefas, etapas ilimitadas, paths)
- Precificado em dólar — com câmbio atual, ~$20 = ~R$115/mês

### Pontos fortes

**Maior catálogo de integrações**: Se um app tem API, provavelmente está no Zapier. Para integrações nichadas — softwares específicos de setor, ferramentas menos conhecidas — o Zapier frequentemente tem quando o Make não tem.

**Interface mais simples**: O Zapier usa um wizard linear (passo a passo) para criar Zaps. Para quem nunca usou automação, é mais fácil de começar.

**Documentação e comunidade**: Muitos tutoriais em YouTube e Google, incluindo em português.

### Pontos fracos

**Plano gratuito muito limitado**: 100 tarefas por mês e apenas 2 etapas. Se você usar para uma automação que roda 20 vezes por dia, em 5 dias você esgotou a cota mensal.

**Custo em dólar**: Para um profissional solo brasileiro, US$20-50/mês pode ser significativo, especialmente quando o câmbio está alto.

**Sem lógica condicional no gratuito**: Filtros e routers exigem plano pago. Para automações simples, não faz diferença. Para automações inteligentes, é uma limitação real.

### Quando usar

- Testar uma automação rápida pela primeira vez
- Integração com um app específico que só está no Zapier
- Quando você precisa de algo funcionando em 15 minutos e não quer aprender uma nova interface

---

## 3. Make — A mais poderosa para gratuito

### O que é

Make (antigo Integromat) é uma plataforma de automação com interface visual em canvas. Em vez do wizard linear do Zapier, você arrasta e conecta módulos em uma tela, criando fluxos que ficam visualmente representados como um diagrama.

Suporta mais de 1.000 apps. Menos que o Zapier, mas cobre todos os apps populares.

### Plano gratuito (2025)

- 1.000 operações por mês (uma "operação" = um módulo executado)
- Cenários de múltiplas etapas ilimitadas
- Filtros condicionais incluídos
- Routers incluídos
- Webhooks incluídos
- Polling a cada 15 minutos
- 2 cenários ativos simultaneamente
- Execução manual ilimitada (para testes)

**Importante sobre operações**: No Make, cada módulo de cada execução conta como uma operação. Um cenário com 5 módulos que roda 100 vezes = 500 operações. Com 1.000 operações mensais, um cenário de 5 módulos pode rodar até 200 vezes por mês antes de atingir o limite.

### Plano pago

- Core: ~$10.59/mês (10.000 operações, cenários ilimitados)
- Pro: ~$18.82/mês (10.000 operações + funcionalidades avançadas)
- Precificado em dólar — com câmbio, ~$10 = ~R$58/mês

### Pontos fortes

**Plano gratuito generoso**: Para a maioria dos casos de uso de um profissional solo iniciando, 1.000 operações mensais são suficientes.

**Interface visual**: Ver o fluxo como um diagrama visual facilita entender o que está acontecendo e identificar problemas.

**Lógica avançada**: Filtros, routers, iteradores, agregadores — funcionalidades avançadas disponíveis no gratuito.

**Mais barato que Zapier**: Quando precisar pagar, o Make é significativamente mais barato para o volume equivalente.

### Pontos fracos

**Curva de aprendizado**: A interface visual é poderosa mas diferente do que a maioria está acostumada. A primeira vez pode ser confusa.

**Catálogo menor**: Menos apps que o Zapier. Para apps muito nichados, pode não ter integração nativa.

**Documentação menos acessível em português**: A maior parte do conteúdo de suporte é em inglês.

### Quando usar

- Automações com mais de 2 etapas
- Quando você precisa de lógica condicional
- Quando o orçamento é limitado e você precisa maximizar o que o gratuito oferece
- Como ferramenta principal de automação no longo prazo

---

## 4. n8n — A opção self-hosted

### O que é

n8n é uma ferramenta de automação open source. Isso significa que o código é aberto — você pode baixar e rodar em um servidor próprio, completamente grátis, sem limites de uso.

### Dois modelos de uso

**n8n Cloud (hospedado pela n8n)**: Similar ao Make/Zapier, você usa na plataforma deles. Plano gratuito com 5 fluxos ativos e 2.500 execuções/mês. Planos pagos a partir de ~$24/mês.

**n8n Self-hosted (você hospeda)**: Você instala em um servidor próprio (como uma VPS na DigitalOcean, Vultr ou servidor local) e usa sem limites de automações, execuções ou etapas. Você paga apenas pelo servidor.

Uma VPS básica na Hostinger ou DigitalOcean custa ~R$30-80/mês e roda n8n com capacidade para centenas de automações simultâneas.

### Pontos fortes

**Gratuito sem limites** (na versão self-hosted): Quando instalado no seu servidor, não há limite de execuções, etapas, ou cenários ativos.

**Código aberto e privacidade**: Seus dados não passam por servidores de terceiros.

**Interface visual**: Similar ao Make, com canvas visual para construir fluxos.

**Comunidade ativa**: Forum, Discord, muitos exemplos de fluxos compartilhados.

**IA nativa**: n8n tem integrações nativas com OpenAI, Anthropic, e outros LLMs, com módulos específicos para construção de agentes.

### Pontos fracos

**Exige configuração técnica**: Instalar e manter um servidor não é trivial para quem não tem background técnico. Você precisa de pelo menos noção básica de linha de comando.

**Manutenção**: Diferente de Make/Zapier, você é responsável por manter o servidor atualizado e funcionando.

**Menor catálogo de integrações nativas**: Embora tenha caminhos para chamar qualquer API via HTTP request, o número de módulos prontos é menor que o Make.

### Quando usar

- Você tem algum conforto com tecnologia e quer zero custo de ferramenta no longo prazo
- Você processa dados sensíveis de clientes e prefere que não passem por servidores de terceiros
- Você quer construir agentes de IA mais avançados (n8n tem módulos específicos para isso)
- Volume alto de execuções onde o Make/Zapier já ficaria caro

---

## 5. Outras ferramentas relevantes no contexto brasileiro

### Pipefy

Ferramenta brasileira de automação de processos. Mais voltada para BPM (gestão de processos de negócio) do que para integração de apps. Tem plano gratuito e interface em português. Boa para fluxos de aprovação e processos internos de equipe.

### Albato

Alternativa ao Zapier com foco em apps populares na Europa oriental e América Latina. Tem alguns apps específicos do mercado brasileiro. Interface em português. Plano gratuito com 100 execuções/mês.

### ActivePieces

Ferramenta open source similar ao n8n, com interface mais moderna e mais fácil de instalar. Crescendo rápido. Se você quer self-hosted mas acha o n8n complicado, é uma boa segunda opção.

---

## 6. Comparação direta: o que cada uma oferece no gratuito

| Critério | Zapier Grátis | Make Grátis | n8n Cloud Grátis | n8n Self-hosted |
|---------|--------------|------------|-----------------|-----------------|
| Execuções/mês | 100 tarefas | 1.000 operações | 2.500 execuções | Ilimitado |
| Etapas por fluxo | 2 | Ilimitadas | Ilimitadas | Ilimitadas |
| Filtros condicionais | Não | Sim | Sim | Sim |
| Fluxos ativos | 5 | 2 | 5 | Ilimitado |
| Integrações | 7.000+ | 1.000+ | 400+ | 400+ |
| Interface | Wizard linear | Canvas visual | Canvas visual | Canvas visual |
| Suporte PT-BR | Parcial | Parcial | Inglês | Comunidade |
| Custo de subir de plano | $20/mês | $10/mês | $24/mês | ~R$50/servidor |

---

## 7. Como escolher baseado na sua situação

**Você está começando do zero e quer o menor atrito possível:**
Comece com o Zapier para entender o conceito. Em 30 dias, mude para o Make.

**Você quer aprender certo da primeira vez sem ficar migrando:**
Vá direto para o Make. A curva é um pouco maior, mas você não vai precisar mudar depois.

**Você tem um volume alto de execuções e não quer pagar:**
Invista algumas horas aprendendo n8n self-hosted. Uma VPS de R$50/mês resolve.

**Você processa dados sensíveis de clientes (saúde, financeiro, jurídico):**
n8n self-hosted — os dados ficam no seu servidor, não passam pelo Make ou Zapier.

**Você precisa de uma integração muito específica (software de nicho):**
Verifica primeiro se está no Zapier. Se não estiver no Make nem no n8n, provavelmente está no Zapier.

**Você quer construir agentes de IA mais avançados:**
n8n tem módulos nativos de IA (AI Agent, Chain, Memory, Tools) que facilitam muito a construção de agentes sem código.

---

## 8. O ecossistema de integrações no contexto brasileiro

Um ponto prático importante: nem toda integração que funciona nos EUA funciona bem ou de forma acessível no Brasil.

**Integrações que funcionam bem:**
- Google (Gmail, Drive, Sheets, Docs, Forms, Calendar) — excelente suporte em todos
- Meta (Instagram, Facebook, WhatsApp Business API) — suporte bom, mas WhatsApp exige aprovação de conta business
- Slack, Notion, Trello, Asana — excelente suporte
- OpenAI, Anthropic (IA generativa) — excelente, mas pago em dólar
- Mailchimp, ActiveCampaign — suporte bom

**Integrações que exigem atenção:**
- WhatsApp: a API oficial exige conta WhatsApp Business verificada. Para automação informal, existem ferramentas não-oficiais (como Zapi, Evolution API, WPPConnect), que funcionam mas não são endossadas pelo Meta e podem ser desativadas.
- Mercado Livre, Mercado Pago: têm APIs mas exigem cadastro como desenvolvedor e têm limitações no plano gratuito
- RD Station, Kommo (CRM brasileiro): presentes no Zapier e Make

**Integrações via webhook ou HTTP request:**
Quando um app específico não tem módulo nativo, você usa um webhook ou chamada HTTP direta. Isso funciona com qualquer app que tenha API — é mais técnico mas totalmente possível.

---

## 9. Instalando e configurando o n8n self-hosted: guia básico

Para quem quer dar o passo do n8n self-hosted, aqui está o processo básico. Não é complicado, mas exige um pouco mais de atenção técnica do que o Make.

### O que você precisa

**Um servidor VPS (Virtual Private Server)**: Servidores na nuvem por assinatura mensal. As opções mais baratas e confiáveis para o Brasil:

- **Hostinger VPS**: planos a partir de ~R$40/mês. Interface em português. Bom para iniciantes.
- **DigitalOcean Droplet**: $6/mês (plano básico). Interface em inglês. Confiável e bem documentado.
- **Vultr**: similar ao DigitalOcean em preço e funcionalidade.

Para rodar n8n com até 100 execuções/hora, 1 vCPU e 1GB RAM já são suficientes.

### Instalação com Docker (recomendada)

Docker é uma ferramenta que empacota aplicativos para rodar de forma isolada. A instalação do n8n via Docker é mais simples do que instalar manualmente.

**Passo 1**: No servidor, instale o Docker:
```bash
curl -fsSL https://get.docker.com | bash
```

**Passo 2**: Crie um arquivo `docker-compose.yml`:
```yaml
version: "3"
services:
  n8n:
    image: n8nio/n8n
    restart: always
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=seu_usuario
      - N8N_BASIC_AUTH_PASSWORD=sua_senha_forte
    volumes:
      - n8n_data:/home/node/.n8n
volumes:
  n8n_data:
```

**Passo 3**: Rode o container:
```bash
docker compose up -d
```

**Passo 4**: Acesse `http://IP_DO_SEU_SERVIDOR:5678` no navegador.

### Configurando um domínio (opcional mas recomendado)

Se você comprar um domínio (ou usar um subdomínio que já tem), pode acessar o n8n pelo endereço `https://automacoes.seusite.com.br` em vez do IP. Isso exige configurar um proxy reverso (Nginx ou Caddy) com certificado SSL. Mais técnico, mas vale para uso profissional.

### Atualizações

Para atualizar o n8n para a versão mais recente:
```bash
docker compose pull
docker compose up -d
```

Faça isso mensalmente para garantir que você tem os últimos módulos e correções de segurança.

---

## Erros comuns

### Erro 1: Escolher pelo nome, não pelos requisitos

"Todo mundo usa Zapier, então vou usar Zapier." Você não está otimizando pelo hype da ferramenta — está otimizando por custo-benefício para o seu caso.

**Mecanismo**: Cada ferramenta foi construída com trade-offs diferentes. Zapier priorizou facilidade e catálogo. Make priorizou poder e eficiência de custo. n8n priorizou liberdade e privacidade.

**Como corrigir**: Liste primeiro o que você precisa: quantas execuções por mês, quantas etapas, precisa de condicionais, precisa de algum app específico, qual orçamento. Depois escolha.

### Erro 2: Não calcular o custo antes de escalar

Você cria uma automação linda, sobe para produção, e no mês seguinte recebe uma cobrança inesperada porque o volume escalou além do plano.

**Mecanismo**: Planos têm limites. Quando você supera, ou a automação para ou você é cobrado pelo excesso.

**Como corrigir**: Antes de escalar uma automação, estime: quantas execuções por dia × etapas por execução × dias do mês = operações/mês. Compare com o seu plano. Se ultrapassar, decida antes se vai pagar o upgrade ou otimizar o fluxo.

### Erro 3: Colocar dados sensíveis em ferramentas sem verificar os termos

Dados de clientes — nome, e-mail, CPF, informações financeiras — passam pelos servidores do Make/Zapier quando você usa essas ferramentas.

**Mecanismo**: Ao conectar um app, a ferramenta de automação atua como intermediária e armazena temporariamente os dados processados.

**Como corrigir**: Para dados muito sensíveis, use n8n self-hosted. Para dados moderamente sensíveis, leia os termos da ferramenta — tanto Make quanto Zapier têm políticas de privacidade razoáveis, mas vale verificar se estão alinhadas com os dados que você processa.

### Erro 4: Não configurar autenticação de forma segura

Usar sua conta pessoal principal do Google para conectar ao Make. Se a conexão for comprometida, o acesso ao seu e-mail inteiro está exposto.

**Mecanismo**: Cada conexão de app tem permissões de acesso. Se o token for vazado ou a plataforma for comprometida, esses acessos ficam expostos.

**Como corrigir**: Para automações de produção, crie contas de serviço separadas (por exemplo, um e-mail específico para automações: "automacoes@seudominio.com"). Limite as permissões ao mínimo necessário.

### Erro 5: Não documentar os fluxos

Você cria 10 fluxos em 3 meses. Depois de 6 meses, esqueceu o que cada um faz, por que foi criado, e o que acontece se você pausá-lo.

**Mecanismo**: Automações são invisíveis quando funcionando. Você só percebe que existem quando quebram.

**Como corrigir**: Mantenha uma planilha simples: nome do fluxo, o que faz, quando foi criado, apps conectados, observações de manutenção.

---

## Exercício prático

Esse exercício é de tomada de decisão, não de construção técnica — mas é igualmente importante.

**Tarefa: Monte seu mapa de ferramentas**

Abra um documento ou planilha e responda:

1. Liste as 5 automações que você identificou na Aula 1 como prioridades.

2. Para cada automação, anote:
   - Quantas etapas estima que vai ter?
   - Precisa de lógica condicional?
   - Quais apps precisam estar conectados?
   - Qual a frequência estimada de execução (por dia)?

3. Calcule para cada automação: execuções/dia × etapas × 30 dias = operações mensais estimadas.

4. Some todas as operações das 5 automações.

5. Com base nesse número, determine:
   - O plano gratuito do Make é suficiente (até 1.000 operações)?
   - Precisa do plano pago do Make (a partir de $10/mês)?
   - O volume é tão alto que vale considerar o n8n self-hosted?

6. Verifique se todos os apps que você precisa estão disponíveis no Make (make.com/integrations). Se algum não estiver, verifique no Zapier.

Entregável: sua tabela de mapeamento com a decisão de ferramenta justificada.

---

## 10. Migrando de uma ferramenta para outra: o que levar em conta

Em algum momento você vai querer migrar — do Zapier para o Make, do Make para o n8n, ou o contrário. Migrações de automação têm armadilhas específicas.

### O que NÃO é portável

Automações não são portáveis de uma ferramenta para outra. Você não exporta um Zap do Zapier e abre no Make. Cada fluxo precisa ser reconstruído na nova ferramenta. Por isso, o custo de migração é real — você precisa reproduzir cada cenário, testar, e ativar novamente.

### Como planejar uma migração

**1. Inventário**: Liste todos os fluxos ativos, o que fazem, e a frequência de uso. Priorize quais migrar primeiro.

**2. Migre em paralelo**: Antes de desativar o fluxo na ferramenta antiga, ative-o na nova e deixe rodar em paralelo por uma semana. Compara os resultados.

**3. Desative, não delete**: Quando migrar para a nova ferramenta, pause o fluxo antigo (não delete). Se algo der errado, você tem o original como referência.

**4. Migre em lotes**: Não migre tudo de uma vez. Migre 2-3 fluxos por semana. Dá tempo para identificar problemas antes de eles se acumularem.

### Quando a migração vale o esforço

A migração vale quando o custo da ferramenta atual está ficando alto, quando você precisa de funcionalidades que a ferramenta atual não tem, ou quando você vai escalar o volume e a ferramenta atual não é viável para esse volume.

A migração não vale quando você está migrando por curiosidade ou por achar que a outra ferramenta é "melhor" de forma abstrata. Automações funcionando têm valor — o custo de refazer tudo precisa ser justificado por benefício concreto.

---

## Resumo

- Zapier: mais fácil, mais integrações, plano gratuito muito limitado (100 tarefas, 2 etapas)
- Make: mais poderoso no gratuito (1.000 operações, etapas ilimitadas, filtros incluídos), melhor custo-benefício
- n8n: open source, auto-hospedado = sem limite de uso pelo custo de um servidor (~R$50/mês), exige mais conhecimento técnico
- Para começar: Make é a melhor escolha entre custo, poder e facilidade
- Para volume alto ou dados sensíveis: n8n self-hosted
- Antes de escolher a ferramenta, calcule: execuções × etapas × dias = operações mensais
- No Brasil: Google, Meta, OpenAI e as principais ferramentas de gestão funcionam bem; WhatsApp Business exige conta verificada para API oficial
- Documente seus fluxos — automações invisíveis que param de funcionar sem aviso são um problema de gestão, não de tecnologia
- Migrações de ferramenta exigem reconstrução completa dos fluxos — só migre quando há benefício concreto justificando o esforço
