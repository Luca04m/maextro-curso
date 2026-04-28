# Aula 5 — Deploy: Como Publicar o que Você Criou sem Pagar Nada no Início

## O que você vai entender nesta aula

Você vai entender o que é deploy, como funciona a publicação de sites na internet, e como usar três plataformas gratuitas (Vercel, Netlify, GitHub Pages) para publicar seus projetos sem gastar nada — com o passo a passo de cada uma.

---

## O que é deploy

"Deploy" é a palavra técnica para "publicar na internet". Quando você cria um site no seu computador ou em uma ferramenta de IA, ele existe apenas onde você está criando — no seu computador ou no ambiente da ferramenta. Deploy é o processo de mover esse site para um servidor conectado à internet, para que qualquer pessoa com o link possa acessar.

Antes de entrar nas ferramentas, você precisa entender três conceitos que aparecem em todo processo de deploy:

**Hosting (hospedagem):** O servidor onde os arquivos do seu site ficam armazenados. Pense como o terreno onde você constrói a casa. Sem hosting, o site não fica acessível.

**Domínio:** O endereço web do site — como `www.clinicaana.com.br`. Domínios são comprados separadamente e custam entre R$30 e R$150 por ano, dependendo da extensão (.com.br, .com, .net, etc.). Para projetos iniciais, todas as plataformas de deploy gratuitas fornecem um subdomínio gratuito (como `clinicaana.vercel.app`).

**HTTPS:** O protocolo seguro de conexão — aquele cadeado que aparece na barra do browser. Todos os serviços de deploy gratuitos mencionados aqui configuram HTTPS automaticamente.

---

## As três plataformas gratuitas

### Vercel — vercel.com

**Plano gratuito:** Generoso. Projetos ilimitados, 100GB de largura de banda por mês, HTTPS automático, subdomínio gratuito `.vercel.app`.

**Melhor para:** Sites e aplicações modernas feitas com frameworks como React, Next.js, Vue. É a mesma empresa que criou o v0, então a integração entre as ferramentas é natural.

**Ponto forte:** Atualizações instantâneas — cada vez que você atualiza o código, o site atualiza em segundos.

**Como funciona o deploy básico na Vercel:**

Existem três formas de fazer deploy na Vercel. Vamos da mais simples para a mais completa.

**Forma 1 — Drag and drop (arrastar e soltar):**
Esta é a forma mais simples. Você não precisa de conta no GitHub, não precisa de configuração.

1. Vá para vercel.com e crie uma conta (pode usar Gmail)
2. No painel principal, procure a opção de "Deploy" ou clique em "Add New > Project"
3. Em alguns planos/contextos, a Vercel oferece upload direto de pasta
4. Arraste a pasta com os arquivos do seu site para a área indicada
5. Aguarde o deploy (geralmente menos de 60 segundos)
6. Você recebe um link como `https://seu-projeto-abc123.vercel.app`

**Forma 2 — Via GitHub (recomendada para projetos que você vai atualizar):**

1. Crie uma conta no GitHub (github.com) — gratuito
2. Crie um repositório novo no GitHub
3. Faça upload dos arquivos do seu projeto para o repositório
4. Na Vercel, conecte com sua conta do GitHub
5. Selecione o repositório do projeto
6. A Vercel detecta automaticamente o tipo de projeto e configura o build
7. Clique em "Deploy"

A vantagem do método GitHub: quando você atualiza o código no GitHub, o site na Vercel atualiza automaticamente.

**Forma 3 — Via CLI (linha de comando):**
Para usuários mais avançados. Instale o CLI da Vercel (`npm install -g vercel`), navegue até a pasta do projeto, rode `vercel`. Não recomendado para iniciantes.

**Configurando um domínio personalizado na Vercel:**

1. Compre um domínio em um registrador (Registro.br para `.com.br`, Namecheap ou Cloudflare para `.com`)
2. No painel do projeto na Vercel, vá em "Settings > Domains"
3. Adicione o domínio comprado
4. A Vercel fornece os registros DNS que você precisa configurar no registrador
5. Após configurar, aguarde até 48 horas para propagação (geralmente menos de 2 horas)
6. HTTPS é configurado automaticamente

---

### Netlify — netlify.com

**Plano gratuito:** 100GB de largura de banda por mês, builds ilimitados, HTTPS automático, subdomínio gratuito `.netlify.app`, formulários gratuitos (até 100 envios/mês).

**Melhor para:** Sites estáticos (HTML, CSS, JavaScript sem framework complexo), sites com formulários de contato, projetos exportados do Lovable ou gerados por IA como arquivos simples.

**Ponto forte:** O Netlify Forms é um diferencial importante. Ele permite que formulários de contato do seu site enviem dados sem precisar configurar nenhum backend. Isso é valioso para iniciantes.

**Deploy via drag and drop no Netlify:**

Esta é a forma mais rápida de publicar um site no Netlify e não requer conta no GitHub.

1. Vá para netlify.com e crie uma conta
2. No painel, você verá uma área escrita "Want to deploy a new site without connecting to Git? Drag and drop your site output folder here"
3. Comprima os arquivos do seu site em uma pasta (não precisa zipar)
4. Arraste a pasta para a área indicada
5. O Netlify faz o upload e em 30 segundos você tem um link como `https://meu-site-random.netlify.app`
6. Você pode renomear para algo como `https://clinicaana.netlify.app`

**Como usar o Netlify Forms:**

Se você exportou uma landing page do Lovable ou criou uma via Cursor com um formulário HTML simples, pode fazer o formulário funcionar de verdade via Netlify Forms sem escrever nenhum código de backend.

No HTML do formulário, adicione o atributo `netlify` à tag `<form>`:

```html
<form name="contato" method="POST" netlify>
  <input type="text" name="nome" placeholder="Seu nome">
  <input type="email" name="email" placeholder="Seu email">
  <textarea name="mensagem" placeholder="Sua mensagem"></textarea>
  <button type="submit">Enviar</button>
</form>
```

Depois do deploy no Netlify, os envios aparecem no painel em "Forms". Você pode configurar para receber por email também.

Você pode pedir para o ChatGPT, Claude ou para a ferramenta que você usou para criar o site adicionar esse atributo: "Adicione o atributo `netlify` na tag form do formulário de contato para funcionar com Netlify Forms."

**Deploy via GitHub no Netlify:**

Funciona de forma idêntica à Vercel: conecte o GitHub, selecione o repositório, configure e deploy automático a cada atualização.

---

### GitHub Pages — pages.github.com

**Plano gratuito:** Totalmente gratuito. Sem limites de largura de banda para uso normal. Subdomínio gratuito `.github.io`.

**Melhor para:** Sites estáticos simples (HTML, CSS, JavaScript). Portfólios, landing pages, sites de documentação.

**Limitação importante:** GitHub Pages suporta apenas sites estáticos. Não funciona para aplicações React sem uma etapa de "build" (processo de compilação que gera os arquivos estáticos). Se você criou algo com Lovable, precisará exportar o código compilado, não o código fonte.

**Como usar o GitHub Pages:**

1. Crie uma conta no GitHub (github.com)
2. Crie um novo repositório com o nome `seuusuario.github.io` (substitua "seuusuario" pelo seu nome de usuário do GitHub)
3. Faça upload dos arquivos HTML, CSS e JS do seu projeto
4. Vá em Settings > Pages
5. Em "Source", selecione "Deploy from a branch" e escolha a branch "main"
6. Aguarde alguns minutos
7. Seu site estará em `https://seuusuario.github.io`

Para projetos em subdomínio (não na raiz), crie um repositório com nome qualquer, ative Pages da mesma forma, e o site ficará em `https://seuusuario.github.io/nome-do-repositorio`.

**Upload de arquivos no GitHub:**

Se você não usou terminal e quer apenas fazer upload:

1. No repositório, clique em "Add file > Upload files"
2. Arraste seus arquivos HTML, CSS e imagens
3. Clique em "Commit changes"
4. Aguarde o Pages atualizar (1-3 minutos)

---

## Como exportar de cada ferramenta de criação

### Exportando do Lovable

O Lovable tem deploy integrado — você clica em "Publish" e o site vai para um subdomínio `.lovable.app`. Para usar Vercel ou Netlify:

1. No Lovable, conecte com GitHub (Settings > GitHub Integration)
2. Isso cria um repositório GitHub com todo o código do projeto
3. Na Vercel ou Netlify, conecte esse repositório

### Exportando do v0

O v0 gera componentes, não projetos completos. Para publicar:

1. Copie o código gerado
2. Crie um projeto Next.js localmente: `npx create-next-app@latest meu-projeto`
3. Cole o componente nos arquivos corretos
4. Faça o deploy na Vercel (que suporta Next.js nativamente)

Para iniciantes, o v0 funciona melhor quando combinado com o Lovable ou quando o objetivo é apenas ver o componente funcionando.

### Exportando do Cursor

O Cursor cria os arquivos diretamente no seu computador. Para publicar:

1. Se é HTML estático: arraste a pasta para Netlify ou GitHub Pages
2. Se é React: faça o build com `npm run build` e faça deploy da pasta `dist` ou `build` na Netlify

### Exportando do Replit

O Replit tem hospedagem integrada. Seu projeto fica em `https://nome-do-projeto.seuusuario.repl.co`. Não precisa de deploy externo — mas o subdomínio não é personalizável no plano gratuito.

---

## Fluxo recomendado para iniciantes

Para os primeiros 30 dias, use este fluxo:

1. **Crie no Lovable** — o processo de criação mais simples
2. **Publique diretamente no Lovable** — subdomínio `.lovable.app` gratuito
3. **Quando precisar de formulário funcionando:** Exporte para GitHub, conecte no Netlify, ative Netlify Forms
4. **Quando o cliente quiser domínio personalizado:** Configure o domínio no Netlify ou Vercel
5. **Compre o domínio quando vender o projeto** — não antes. Não gaste dinheiro em domínio enquanto o projeto está em criação

Este fluxo minimiza custo, complexity e tempo de setup.

---

## Sobre custos reais

É importante ser direto sobre o que é gratuito e o que custa.

**Gratuito para sempre:**
- Hosting básico em Vercel, Netlify e GitHub Pages
- Subdomínio `.vercel.app`, `.netlify.app`, `.github.io`
- HTTPS (certificado de segurança)
- Deploy automático via GitHub

**Não é gratuito:**
- Domínio personalizado: R$30-150/ano dependendo da extensão
- Planos pagos das ferramentas de criação para volumes maiores

**Para os primeiros 30 dias, você pode criar e publicar projetos reais sem gastar nada.**

Quando você começa a trabalhar com clientes, inclua o custo do domínio no orçamento do projeto. É um custo pequeno que faz o projeto parecer muito mais profissional.

---

## DNS: o que você precisa saber para configurar domínios

Você não precisa entender DNS profundamente, mas precisa saber o básico para não ficar preso quando um cliente pede domínio personalizado.

DNS (Domain Name System) é o sistema que transforma um endereço legível (`www.clinicaana.com.br`) no endereço técnico do servidor onde o site está hospedado.

Quando você compra um domínio e quer apontá-lo para Vercel ou Netlify, precisa configurar dois tipos de registro:

**Registro A:** Aponta o domínio raiz (clinicaana.com.br) para o IP do servidor. A Vercel e Netlify fornecem o IP que você deve usar.

**Registro CNAME:** Aponta o subdomínio `www` (www.clinicaana.com.br) para o endereço da sua plataforma de hosting. Formato: `www CNAME clinicaana.vercel.app`

Na prática:
1. Vercel ou Netlify fornecem os registros exatos que você precisa configurar
2. Você acessa o painel do registrador onde comprou o domínio
3. Localiza a seção de DNS ou "Gerenciar DNS"
4. Adiciona os registros fornecidos
5. Aguarda (até 48h, geralmente menos de 2h)

Se você travar nessa etapa, qualquer suporte técnico do registrador de domínio ajuda — é uma operação padrão.

---

## Erros comuns

**Erro 1: Comprar domínio antes de terminar o projeto.**
O mecanismo: domínios custam dinheiro e criam uma urgência artificial. Crie o projeto até estar aprovado pelo cliente antes de comprar o domínio.

**Erro 2: Tentar fazer deploy antes de entender como o projeto foi criado.**
O mecanismo: um projeto React não pode ser hospedado como HTML estático — precisa de um processo de build primeiro. Um projeto HTML estático não precisa de build. Entender qual é o seu caso evita horas de confusão.

**Erro 3: Não configurar HTTPS no domínio personalizado.**
O mecanismo: browsers modernos mostram aviso de segurança em sites sem HTTPS, o que afasta visitantes. Vercel e Netlify configuram HTTPS automaticamente quando você adiciona um domínio.

**Erro 4: Esquecer de testar o site após o deploy.**
O mecanismo: o processo de deploy pode introduzir pequenas diferenças de como o site aparecia localmente. Sempre abra o link publicado e teste como usuário final.

**Erro 5: Usar o mesmo projeto para múltiplos clientes sem isolar os projetos.**
O mecanismo: projetos de clientes diferentes devem estar em repositórios diferentes. Misturar em um único repositório cria confusão e risco de mostrar dados de um cliente para outro acidentalmente.

---

## Exercício prático

Publique o projeto que você criou na Aula 4 usando o seguinte roteiro:

**Opção A — Direto pelo Lovable:**
1. Abra seu projeto no Lovable
2. Clique em "Publish" (botão no canto superior direito)
3. Aguarde o deploy
4. Copie o link publicado
5. Abra no seu celular e confirme que funciona

**Opção B — Via Netlify com drag and drop:**
1. No projeto do Lovable, acesse o código (botão "Code" no canto superior)
2. Exporte os arquivos (ou peça para o Cursor criar um arquivo HTML estático equivalente)
3. Vá para netlify.com e faça login
4. Arraste a pasta com os arquivos para a área de deploy
5. Aguarde o link ser gerado
6. Teste no celular

O objetivo: ter um link que você possa enviar para qualquer pessoa e ela consiga acessar. Quando você tiver esse link, o projeto está publicado.

---

## Resumo

- Deploy é o processo de publicar um site na internet — mover de onde você criou para um servidor acessível para qualquer pessoa
- Três plataformas gratuitas excelentes: Vercel (melhor para React/Next.js), Netlify (melhor para sites estáticos e formulários), GitHub Pages (melhor para HTML simples)
- Todas as três oferecem subdomínio gratuito, HTTPS automático e plano gratuito suficiente para projetos iniciais
- Netlify Forms permite formulários de contato funcionais sem configurar backend — apenas adicione `netlify` na tag `<form>`
- O fluxo recomendado para iniciantes: criar no Lovable, publicar direto pelo Lovable, migrar para Netlify quando precisar de formulário funcionando
- Domínios personalizados custam R$30-150/ano — compre apenas quando o projeto estiver aprovado e você for cobrar por ele
- Configurar DNS para domínio personalizado requer dois registros (A e CNAME) que Vercel e Netlify fornecem — é um processo guiado
