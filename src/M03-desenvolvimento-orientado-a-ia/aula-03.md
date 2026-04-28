# Aula 3 — Ferramentas de Geração de Código com IA: Lovable, Cursor, v0 e Alternativas Gratuitas

## O que você vai entender nesta aula

Você vai conhecer as ferramentas reais disponíveis hoje para criar projetos com IA, entender o que cada uma faz bem, quais são gratuitas, quais têm custos, e como escolher a ferramenta certa para cada tipo de projeto.

---

## O problema da escolha de ferramentas

Existe uma armadilha no início dessa jornada: tentar aprender todas as ferramentas ao mesmo tempo. O mercado de ferramentas de criação com IA cresceu de forma explosiva em 2024-2025. Existem dezenas de opções — e novas aparecem toda semana.

A abordagem correta é diferente: entender o mapa de ferramentas (o que cada categoria faz), escolher uma ferramenta por categoria para dominar primeiro, e expandir depois.

Existem dois grandes grupos de ferramentas para criação com IA:

**Ferramentas baseadas em browser (no-code/low-code):** Você usa tudo dentro de um site, sem instalar nada. Perfeito para iniciantes. Você descreve, a ferramenta gera, você vê o resultado, você publica. Não requer terminal, não requer instalar Node.js, não requer configuração técnica.

**Ferramentas de IDE (editores de código com IA):** Você instala um programa no seu computador (um editor de código com IA integrada). Mais poderoso, mas requer uma instalação inicial e alguma familiaridade com a estrutura de projetos. Indicado para quem quer mais controle ou já tem alguma base técnica.

Para este módulo, vamos focar em ferramentas baseadas em browser primeiro — porque elas eliminam a fricção técnica inicial — e cobrir os editores com IA como uma evolução natural.

---

## Lovable — lovable.dev

**Categoria:** Browser-based, no-code/low-code
**Plano gratuito:** Sim — 5 mensagens por dia no plano free; plano pago a partir de $20/mês
**Melhor para:** Iniciantes, prototipagem rápida, apps completos com interface

Lovable é possivelmente a ferramenta mais acessível para quem está começando do zero. Você acessa lovable.dev, cria uma conta, e a interface principal é uma caixa de texto: "O que você quer construir?"

Você descreve o projeto em linguagem natural. Lovable gera não apenas o visual, mas também a estrutura completa do projeto — arquivos organizados, componentes separados, código limpo. O resultado aparece ao vivo enquanto você conversa.

**O que diferencia o Lovable:**

Ao contrário de ferramentas que geram apenas HTML estático, o Lovable usa React — uma das principais tecnologias para criar interfaces web modernas. Isso significa que os projetos gerados têm a mesma base técnica que startups de verdade usam.

Você não precisa saber o que é React para usar. Mas quando você quiser escalar o projeto ou passar para um desenvolvedor, o código está em uma base profissional.

**Funcionalidades práticas do Lovable:**

- Preview em tempo real: você vê o resultado enquanto conversa
- Histórico de versões: você pode voltar para qualquer versão anterior se algo der errado
- Deploy integrado: você publica com um clique no subdomínio gratuito `.lovable.app`
- Domínio personalizado: possível no plano pago
- Integração com Supabase: para adicionar banco de dados e autenticação quando necessário
- Exportação para GitHub: você pode baixar o código completo

**Como usar o Lovable:**

1. Acesse lovable.dev e crie uma conta
2. Clique em "New Project"
3. Na caixa de texto, escreva seu prompt descrevendo o projeto
4. Aguarde a geração (normalmente 30-90 segundos)
5. Veja o preview, identifique o que precisa ajustar
6. Continue a conversa com prompts de refinamento
7. Quando estiver satisfeito, clique em "Publish" para publicar

**Exemplo de prompt para Lovable:**

```
Crie uma landing page para uma nutricionista chamada Dra. Ana Lima, 
especializada em nutrição funcional em Goiânia. O público são mulheres 
de 30-50 anos que querem emagrecer de forma saudável sem dietas restritivas.

Design: cores verdes e brancas, visual clean e natural.

Seções:
1. Hero com foto placeholder, headline "Emagreça de forma duradoura com 
   uma abordagem que respeita seu corpo" e CTA "Agendar consulta gratuita"
2. Apresentação breve da nutricionista (2 parágrafos fictícios sobre 
   formação e abordagem)
3. Serviços: consulta presencial, acompanhamento online, plano alimentar 
   personalizado — cada um com ícone e descrição curta
4. Depoimentos: 3 cards com nome fictício, foto avatar, texto e 5 estrelas
5. Formulário de contato com nome, email, telefone e mensagem
6. Footer com endereço fictício, redes sociais e WhatsApp

Botão de WhatsApp flutuante no canto inferior direito em toda a página.
```

**Limitação importante do plano free:** 5 mensagens por dia. Em um projeto simples, você pode criar uma landing page completa em 5-8 mensagens se for eficiente. Para projetos mais longos, o limite pode ser restritivo.

---

## v0 — v0.dev

**Categoria:** Browser-based, geração de componentes
**Plano gratuito:** Sim — créditos mensais generosos no plano free
**Melhor para:** Gerar componentes específicos, interfaces de UI, prototipagem de elementos

v0 é uma ferramenta da Vercel (a empresa por trás da plataforma de deploy mais popular para projetos web modernos). A especialidade do v0 é gerar componentes de interface: um formulário de contato, um card de produto, uma navbar, uma tabela de preços.

Diferentemente do Lovable, que foca em criar páginas completas e aplicações, o v0 se destaca em criar peças que você depois conecta ou usa de referência.

**O que diferencia o v0:**

O v0 usa shadcn/ui — uma biblioteca de componentes de interface que é o padrão atual da indústria para apps modernos. O código gerado é limpo, acessível e profissional.

Você pode copiar o código gerado e colar em qualquer projeto que use React. Ou pode pedir para o v0 criar uma página completa e gerar o código para baixar.

**Como usar o v0:**

1. Acesse v0.dev e crie uma conta com Google ou GitHub
2. Na caixa principal, descreva o componente ou página que quer criar
3. O v0 gera múltiplas versões — você pode escolher entre elas
4. Refine com conversa
5. Copie o código ou exporte para um projeto

**Exemplos de prompts eficazes no v0:**

```
Crie um formulário de cadastro para lista de espera de um produto. 
Campos: nome, email, número de WhatsApp, área de atuação (dropdown). 
Visual limpo com fundo branco. Botão de envio azul. 
Mensagem de confirmação após envio.
```

```
Crie uma seção de preços com 3 planos: Básico (gratuito), 
Profissional (R$97/mês) e Empresarial (R$297/mês). 
Cada plano com 5 features, botão de CTA e destaque no plano do meio. 
Cores: roxo como cor de destaque.
```

```
Crie um card de depoimento com: foto circular do cliente, nome, 
cargo, empresa, texto do depoimento e avaliação em estrelas. 
Visual elegante com sombra sutil.
```

**Diferença prática entre v0 e Lovable:** O Lovable cria projetos completos e os hospeda. O v0 cria componentes e páginas com foco na qualidade do código — você precisa de um passo extra para publicar. Para iniciantes querendo publicar rapidamente, o Lovable é mais direto. Para quem quer aprender mais sobre o processo ou precisa de componentes específicos, o v0 é excelente.

---

## Cursor — cursor.com

**Categoria:** Editor de código (IDE) com IA integrada
**Plano gratuito:** Sim — plano free com limitações; Pro a partir de $20/mês
**Melhor para:** Usuários que querem mais controle, projetos maiores, quem tem alguma familiaridade com desenvolvimento

Cursor é um editor de código — pense no Word, mas para escrever código. A diferença é que o Cursor tem IA profundamente integrada. Você conversa com a IA dentro do editor, ela lê todos os seus arquivos, entende o contexto do projeto e faz mudanças diretamente.

O Cursor é baseado no VS Code (o editor de código mais popular do mundo, gratuito do Microsoft). Se você já usou VS Code, Cursor vai parecer familiar. Se não usou, parece um editor de código normal com um chat do lado.

**O que diferencia o Cursor:**

Enquanto Lovable e v0 são ferramentas de geração, o Cursor é uma ferramenta de desenvolvimento assistido. Você tem controle total sobre cada arquivo, cada linha de código. A IA ajuda, mas você vê e pode editar tudo.

Isso é mais poderoso — mas também requer mais comprometimento de aprendizado.

**Como instalar o Cursor:**

1. Acesse cursor.com
2. Clique em Download
3. Instale como qualquer outro programa (Windows, Mac ou Linux)
4. Na primeira abertura, crie uma conta
5. O plano free dá acesso ao essencial

**Como usar o Cursor:**

1. Instale e abra o Cursor
2. Crie uma nova pasta no seu computador para o projeto
3. Abra essa pasta no Cursor (File > Open Folder)
4. Use o atalho Ctrl+L (ou Cmd+L no Mac) para abrir o chat da IA
5. Descreva o que você quer criar
6. O Cursor vai criar os arquivos necessários e mostrar as mudanças
7. Aceite as mudanças sugeridas
8. Use o terminal integrado (Ctrl+`) para rodar o projeto localmente

**Exemplo de fluxo no Cursor:**

```
Usuário: "Crie uma landing page completa para um consultor de marketing 
digital. Precisa de: hero section, serviços, sobre mim, depoimentos e 
formulário de contato. Use HTML, CSS e JavaScript vanilla (sem frameworks). 
Cores: preto e dourado. Tom: premium e confiante."

Cursor: [cria index.html, style.css, script.js com todo o conteúdo]

Usuário: "O formulário de contato não tem validação. Adicione validação 
client-side para email e campos obrigatórios."

Cursor: [modifica script.js com a validação]
```

**Para quem é o Cursor:** Se você não tem nenhuma base técnica e quer publicar algo rápido, comece com Lovable. Se você quer entender mais o processo, tem paciência para aprender alguns conceitos básicos, ou vai criar projetos frequentes, o Cursor vai servir melhor a longo prazo.

---

## Replit — replit.com

**Categoria:** IDE online (browser-based), com hospedagem integrada
**Plano gratuito:** Sim — plano free funcional; planos pagos a partir de $25/mês
**Melhor para:** Experimentação, projetos que precisam de backend simples, aprendizado

Replit é diferente dos outros: é um ambiente de desenvolvimento completo que roda no browser. Você não instala nada, mas tem acesso a um "computador virtual" onde pode rodar qualquer linguagem de programação.

A Replit tem um assistente de IA chamado Replit Agent que funciona de forma similar ao Lovable — você descreve o que quer, ele cria.

**O que diferencia o Replit:**

A principal vantagem é que o Replit pode rodar código que precisa de um servidor — não apenas sites estáticos. Se você precisar de um backend simples (um sistema de envio de email, uma API básica, um banco de dados leve), o Replit consegue hospedar isso gratuitamente.

A desvantagem: o plano gratuito tem limitações de uso (os projetos ficam "dormindo" e demoram para acordar quando acessados).

**Como usar o Replit:**

1. Acesse replit.com e crie uma conta
2. Clique em "Create Repl"
3. Escolha "HTML, CSS, JS" para sites simples
4. Use o chat da IA para criar o projeto
5. O site fica automaticamente hospedado em um subdomínio `.replit.app`

---

## Outras ferramentas relevantes

### Bolt.new — bolt.new

**Categoria:** Browser-based
**Plano gratuito:** Sim — créditos mensais

Bolt é similar ao Lovable em propósito — você descreve um projeto, ele gera código completo e funcional. Uma diferença: o Bolt usa StackBlitz como base, o que significa que o código roda diretamente no browser sem precisar de um servidor externo.

Boa alternativa quando o Lovable estiver com limite de mensagens esgotado no plano free.

### Claude.ai e ChatGPT — para geração de HTML estático

**Categoria:** Chat com geração de código
**Plano gratuito:** Sim (com limitações)

Para projetos muito simples — uma página de confirmação, um card de produto, um template de email — você pode simplesmente pedir para o Claude ou ChatGPT gerar o HTML diretamente no chat, copiar o código, salvar como `index.html` e abrir no browser.

Não tem preview em tempo real, não tem deploy integrado, mas o código funciona. Para prototipagem rápida ou para aprender como o código é estruturado, é uma opção válida e gratuita.

---

## Como escolher a ferramenta certa para cada situação

Aqui está um guia de decisão direto:

**Use Lovable quando:**
- Você quer criar e publicar algo rápido
- É uma landing page, portfólio ou aplicativo com interface
- Você não quer instalar nada
- É seu primeiro projeto com IA

**Use v0 quando:**
- Você quer gerar um componente específico de alta qualidade
- Precisa de código limpo para usar em outro projeto
- Está prototipando elementos de interface (pricing, forms, cards)

**Use Cursor quando:**
- Você quer mais controle sobre o projeto
- Vai criar múltiplos projetos e quer uma ferramenta mais poderosa
- Quer entender mais o processo de desenvolvimento
- O projeto é mais complexo do que uma única página

**Use Replit quando:**
- O projeto precisa de backend (processamento no servidor)
- Quer experimentar sem instalar nada
- Está aprendendo e quer ver como diferentes tipos de projetos funcionam

**Use Claude/ChatGPT direto quando:**
- É algo muito simples (página de agradecimento, template de email)
- Está fazendo uma demonstração rápida
- Quer entender como o código é escrito

---

## Tabela comparativa das principais ferramentas

| Ferramenta | Plano Free | Publica direto | Precisa instalar | Melhor uso |
|------------|-----------|----------------|------------------|------------|
| Lovable | 5 msgs/dia | Sim | Não | Landing pages completas |
| v0 | Créditos mensais | Não direto | Não | Componentes e UI |
| Cursor | Limitado | Não (precisa de deploy) | Sim | Projetos maiores |
| Replit | Sim (limitado) | Sim | Não | Backend simples |
| Bolt.new | Créditos mensais | Sim | Não | Alternativa ao Lovable |

---

## O ciclo de uso real

Na prática, muitos criadores usam mais de uma ferramenta para o mesmo projeto. Um fluxo comum:

1. **Lovable** — para criar a landing page completa rapidamente
2. **v0** — para gerar um componente específico que ficou melhor lá (como uma tabela de preços)
3. **Cursor** — para fazer ajustes finos no código se necessário
4. **Vercel** (plataforma de deploy) — para publicar o resultado final com domínio personalizado

Você não precisa dominar todas agora. O objetivo é entender o que cada uma faz para poder escolher a ferramenta certa na hora certa.

---

## Erros comuns

**Erro 1: Pular de ferramenta em ferramenta sem criar nada.**
O mecanismo: a variedade de ferramentas cria a ilusão de que você precisa encontrar a "certa" antes de começar. Isso é procrastinação disfarçada. A verdade é que qualquer uma das ferramentas listadas aqui funciona para os projetos que você vai criar nos próximos 6 meses. Escolha uma e crie algo até o fim.

**Erro 2: Superestimar o que o plano gratuito entrega.**
O mecanismo: planos gratuitos têm limites reais. No Lovable, 5 mensagens por dia significa que projetos complexos vão se arrastar. No Cursor, o plano free tem menos acesso a modelos avançados. Isso não é problema — é importante saber com o que você está trabalhando.

**Erro 3: Não testar o resultado antes de entregar.**
O mecanismo: o código gerado por IA é geralmente funcional, mas tem bugs sutis. Um link que não vai para lugar nenhum, um formulário que não envia, uma imagem que não carrega. Sempre teste como usuário final antes de apresentar para qualquer cliente ou publicar para o público.

**Erro 4: Confundir "funciona no meu computador" com "funciona para todos".**
O mecanismo: quando você testa localmente (no seu computador), as condições são diferentes de quando o site está publicado. Conexão lenta, dispositivos diferentes, browsers diferentes. Teste em pelo menos duas condições diferentes: no seu celular com wi-fi e no seu celular com 4G.

**Erro 5: Não salvar o código antes de grandes iterações.**
O mecanismo: quando você pede mudanças grandes, a IA pode reescrever seções que estavam boas. Ferramentas com histórico de versões (Lovable, Cursor) resolvem isso automaticamente. Em ferramentas sem histórico, salve uma cópia do código antes.

---

## Exercício prático

Crie sua conta em pelo menos duas ferramentas agora, antes de precisar delas:

1. Acesse **lovable.dev** e crie sua conta (pode ser com Gmail)
2. Acesse **v0.dev** e crie sua conta (pode ser com Github ou Gmail)
3. Opcional: Acesse **cursor.com** e baixe o instalador para quando estiver pronto

Não precisa criar nada ainda — apenas ter as contas prontas elimina a fricção quando você precisar usar.

Se quiser dar um passo a mais: no Lovable, abra um novo projeto, cole o prompt que você desenvolveu nas aulas anteriores e veja o que acontece. Observe o processo de geração. Não se preocupe com perfeição ainda — apenas observe.

---

## Resumo

- As ferramentas se dividem em duas categorias: browser-based (sem instalar nada) e editores de código com IA (instalação necessária, mais controle)
- **Lovable** (lovable.dev) é a melhor opção para iniciantes que querem criar e publicar rapidamente — plano gratuito com 5 mensagens/dia
- **v0** (v0.dev) se destaca na geração de componentes específicos com código de alta qualidade
- **Cursor** (cursor.com) oferece mais controle para projetos maiores, requer instalação
- **Replit** (replit.com) é útil quando o projeto precisa de backend e você não quer instalar nada
- A escolha da ferramenta depende do projeto: velocidade de publicação vs. controle vs. complexidade
- Na prática, usar mais de uma ferramenta no mesmo projeto é normal e eficiente
- O mais importante é escolher uma e criar algo até o fim — não explorar todas sem concluir nenhum projeto
