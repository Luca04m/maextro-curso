# Aula 4 — Do Prompt ao Protótipo Funcional: O Processo Completo

## O que você vai entender nesta aula

Você vai aprender o processo completo de transformar uma ideia em um protótipo funcional usando IA — desde o primeiro prompt até o resultado que você pode mostrar para um cliente. Inclui como estruturar a conversa com a IA, como iterar sem perder o que está bom, e como lidar com os momentos em que a IA gera algo errado.

---

## O que é um protótipo funcional

Existe uma distinção importante que vale entender desde o início.

**Wireframe:** Esboço em preto e branco mostrando a estrutura de uma página — onde vai o menu, onde vai o texto, onde vai o botão. Sem cores, sem detalhes visuais.

**Mockup:** Representação visual estática da página final — com cores, fontes e imagens, mas sem funcionalidade real. Você olha, mas não pode clicar.

**Protótipo funcional:** Uma versão navegável e interativa — você pode clicar nos botões, preencher formulários, ver animações. Ainda não é o produto final, mas funciona de verdade.

**Produto final:** O resultado acabado, testado, publicado.

Quando usamos ferramentas de IA para criação, pulamos direto para o protótipo funcional — o Lovable e o Cursor não geram mockups estáticos. Eles geram código que roda, botões que funcionam (ou deveriam funcionar), formulários que podem ser preenchidos.

Isso é uma vantagem enorme: você pode mostrar para um cliente um protótipo funcional em horas, não em semanas.

---

## O processo completo em 6 etapas

### Etapa 1: Especificação — definir antes de criar

O trabalho antes do primeiro prompt é o mais importante. Muitos iniciantes pulam essa etapa e depois frustram com o resultado.

Antes de abrir qualquer ferramenta, documente:

**O objetivo de negócio:**
Qual problema este projeto resolve? Para quem? O que muda na vida do usuário depois que ele interage com esta página ou ferramenta?

**O perfil do usuário:**
Quem exatamente vai usar isso? Idade aproximada, nível técnico, dispositivo principal (mobile ou desktop), nível de paciência com tecnologia.

**O fluxo principal:**
Descreva em linguagem simples o caminho que o usuário ideal percorre. Exemplo: "O usuário chega pela propaganda, vê a oferta, clica no botão de WhatsApp, manda mensagem para o número da empresa."

**Os elementos necessários:**
Liste as seções, funcionalidades e conteúdo que precisam estar presentes. Seja específico: não "seção de depoimentos" mas "3 depoimentos de clientes reais com foto, nome e cidade".

**As restrições:**
Existe algo que NÃO pode estar na página? Algum elemento que o cliente não quer? Cores que não podem aparecer? Concorrentes que não devem ser mencionados?

Com essas respostas documentadas, seu primeiro prompt vai ser substancialmente melhor.

### Etapa 2: O prompt fundador

O primeiro prompt define a arquitetura do projeto. Mude-o no meio do caminho e você pode perder coerência na estrutura.

Um bom prompt fundador tem entre 200 e 400 palavras. Isso pode parecer muito, mas considere: você está dando instruções para uma ferramenta construir algo que levaria um desenvolvedor horas de trabalho. Vale a pena ser completo.

Estrutura de um prompt fundador eficaz:

```
[CONTEXTO DO NEGÓCIO]
Crie [tipo de projeto] para [nome fictício ou real do negócio], 
[descrição do negócio em 1-2 frases]. 

[PÚBLICO-ALVO]
O público principal é [descrição específica do usuário].

[TOM E IDENTIDADE VISUAL]
Tom: [adjetivos que descrevem a voz da comunicação]
Cores: [paleta específica]
Tipografia: [se relevante]
Estilo visual: [referências ou descrição — minimalista, vibrante, corporativo, etc.]

[ESTRUTURA DA PÁGINA]
Seções em ordem:
1. [Nome da seção] — [descrição do que deve conter]
2. [Nome da seção] — [descrição do que deve conter]
[...]

[ELEMENTOS FUNCIONAIS]
- [Elemento: botão, formulário, animação, contador, etc.]
- [Elemento...]

[CALL TO ACTION]
CTA principal: [ação específica que o usuário deve fazer]
Texto do botão: [sugestão de texto]
```

Você não precisa usar exatamente esse formato — mas precisa cobrir essas informações.

### Etapa 3: Avaliação do primeiro resultado

Quando a IA gerar o primeiro resultado, faça uma pausa antes de reagir. Não responda imediatamente. Avalie.

Abra o preview. Faça estas perguntas:

**Estrutura está correta?**
As seções esperadas aparecem? Na ordem correta? Falta alguma seção?

**Conteúdo é adequado?**
O texto gerado faz sentido para o negócio? Existe texto placeholder que não foi substituído?

**Visual está adequado para o público?**
Alguém do público-alvo ficaria confortável com esse visual? Parece profissional para o contexto?

**Mobile está funcionando?**
Redimensione a janela do browser para testar mobile, ou use as ferramentas de desenvolvedor do browser (F12 no Chrome, depois ícone de celular).

**Os elementos interativos funcionam?**
Clique nos botões. Preencha os formulários. Os menus abrem?

Faça anotações antes de começar a iterar. "O hero está ótimo. A seção de serviços precisa de mais espaçamento. O formulário não tem validação. O footer está faltando o endereço."

### Etapa 4: Iteração estruturada

A iteração mais eficiente segue uma ordem específica:

**Primeiro, resolva problemas estruturais:** elementos que estão completamente errados ou faltando. Não adianta ajustar detalhes visuais se a estrutura básica está errada.

**Segundo, ajuste o conteúdo:** substitua textos genéricos por conteúdo real ou específico. A IA frequentemente gera texto genérico que precisa ser personalizado.

**Terceiro, refine o visual:** cores, espaçamento, tipografia, tamanhos. Esses ajustes são os mais granulares e devem vir depois que a estrutura está correta.

**Quarto, adicione funcionalidades:** validações, animações, comportamentos interativos.

Um erro comum é fazer ajustes visuais enquanto a estrutura ainda está errada. Você acaba refazendo o mesmo trabalho.

**Como formular prompts de iteração:**

Seja cirúrgico. Não diga "melhore a página". Diga:

- "A seção de serviços está com os cards muito juntos. Adicione mais espaçamento entre eles e entre a seção e a anterior."
- "O título principal está pequeno demais em mobile. Ajuste para que seja legível em tela de 375px de largura."
- "O botão de WhatsApp deve abrir o aplicativo com a mensagem pré-preenchida: 'Olá, vim pelo site e gostaria de mais informações.' Use o link: https://wa.me/5500000000000?text=Olá,%20vim%20pelo%20site%20e%20gostaria%20de%20mais%20informações."
- "Adicione uma animação sutil de fade-in quando o usuário rolar até cada seção."

Quanto mais específico for o pedido, menor a chance de a IA mudar algo que estava correto.

### Etapa 5: Gestão de problemas

A IA vai gerar algo errado em algum momento. Isso não é exceção — é parte do processo. O que diferencia quem usa bem essas ferramentas é saber como responder quando isso acontece.

**Quando a IA "inventa" informações:**
A IA pode criar depoimentos que não fazem sentido para o negócio, inventar números irreais ou descrever serviços de forma imprecisa. Corrija especificando: "O depoimento da Maria Silva precisa mencionar que ela usou o serviço de clareamento dental, não o de aparelho invisível."

**Quando a IA destrói algo que estava bom:**
Ferramentas com histórico de versões (Lovable) permitem voltar. No Cursor, use Ctrl+Z para desfazer. Se não tiver opção de desfazer, você pode descrever o estado anterior: "O header que você gerou anteriormente estava melhor. O menu era horizontal com fundo transparente que ficava fixo ao rolar. Restaure esse comportamento."

**Quando a IA não consegue resolver um problema:**
Se você pediu 3 vezes para corrigir um problema e o resultado continua errado, reformule a abordagem. Em vez de dizer "o botão não está no lugar certo", descreva exatamente onde deveria estar: "O botão deve estar centralizado, com 40px de margem superior em relação ao texto acima, e deve ter 200px de largura máxima."

**Quando a IA gera código com erros:**
Algumas ferramentas mostram o código diretamente. Se você vir mensagens de erro, cole o erro na conversa com a IA: "Estou recebendo este erro: [cole o texto do erro]. Como corrigir?" A IA geralmente resolve.

### Etapa 6: Validação antes de apresentar

Antes de mostrar o protótipo para qualquer pessoa, faça um teste como usuário externo — não como criador.

Peça para outra pessoa usar. Observe onde ela hesita, onde ela fica confusa, onde ela não encontra o que precisa. Essas observações valem mais do que qualquer análise técnica.

Se não tiver outra pessoa disponível, espere algumas horas e teste você mesmo com "olhos frescos". Erros óbvios ficam invisíveis quando você está imerso no projeto.

---

## Um exemplo completo: do zero ao protótipo

Vamos acompanhar o processo completo de criação de uma landing page para um serviço de tutoria online. Isso é real — você pode replicar esse fluxo.

**Contexto:**
Cliente: professora de inglês que quer oferecer aulas online via Zoom para adultos.

**Etapa 1 — Especificação:**

*Objetivo:* Capturar leads de adultos interessados em aulas de inglês online. Ação principal: preencher formulário de contato ou clicar no WhatsApp.

*Usuário:* Adultos de 25-45 anos que precisam de inglês para trabalho ou viagem. Usam principalmente celular. Têm pouco tempo.

*Fluxo:* Chega via anúncio → vê a proposta → vê prova de resultado → clica no contato.

*Elementos:* Hero com proposta de valor, método de ensino (3 passos), depoimentos (3), formulário de interesse, FAQ curto.

*Restrições:* Nenhuma.

**Prompt fundador:**

```
Crie uma landing page para a professora de inglês Ana Costa, que oferece 
aulas de inglês online via Zoom para adultos no Brasil. Ela se especializa 
em inglês para profissionais — pessoas que precisam do idioma para trabalho 
ou viagens internacionais.

Público: adultos de 25-45 anos, profissionais, usam principalmente celular, 
querem resultado rápido e prático.

Tom: profissional mas acolhedor. Confiante sem ser arrogante. 
Direto ao ponto — o público não tem tempo a perder.

Cores: azul e dourado, com branco. Visual clean e profissional.

Estrutura da página:
1. HERO: Headline "Fale inglês com confiança em 6 meses — sem sair de casa", 
   subheadline explicando que as aulas são ao vivo, personalizadas e focadas 
   em resultado. CTA: botão "Quero minha aula experimental gratuita".
   
2. COMO FUNCIONA: 3 steps simples com ícones: (1) Diagnóstico gratuito, 
   (2) Plano personalizado, (3) Aulas ao vivo toda semana.
   
3. SOBRE A PROFESSORA: Foto placeholder, nome Ana Costa, breve bio fictícia 
   (formada em Letras, 8 anos de experiência, moradora nos EUA por 3 anos, 
   500 alunos formados).
   
4. DEPOIMENTOS: 3 cards com nome fictício, profissão e texto curto 
   (máx 3 linhas). Exemplo: "Consegui uma promoção depois de 6 meses 
   com a professora Ana. Meu inglês mudou." — Carlos M., Engenheiro.
   
5. FORMULÁRIO DE INTERESSE: Nome, Email, WhatsApp, 
   "Qual seu nível de inglês?" (dropdown: iniciante, intermediário, avançado).
   Botão verde: "Garantir minha aula gratuita".
   
6. FAQ: 4 perguntas com respostas simples: Quanto custa? Qual horário? 
   Precisa de material? Como funciona a aula experimental?
   
7. FOOTER: Nome da professora, email fictício, link para Instagram, 
   WhatsApp.

ELEMENTOS ADICIONAIS:
- Botão flutuante de WhatsApp sempre visível no canto inferior direito
- Contador fictício: "127 alunos formados este ano"
- Badge de garantia: "7 dias de garantia ou devolução total"

O formulário não precisa funcionar de verdade — apenas ter o visual correto.
```

**Resultado após o primeiro prompt:** A IA vai gerar uma landing page com a estrutura completa. Suponha que o resultado está 70% bom.

**Iteração 1 — Problema estrutural:**
"O formulário de interesse aparece depois do FAQ. Mova-o para depois dos depoimentos, antes do FAQ. A sequência correta é: hero > como funciona > sobre > depoimentos > formulário > FAQ > footer."

**Iteração 2 — Conteúdo:**
"O texto do hero está muito genérico. Substitua a subheadline por: 'Aulas individuais ao vivo com método comprovado. Sem turma grande, sem material antigo, sem desperdício de tempo.'"

**Iteração 3 — Visual mobile:**
"No mobile, os 3 steps de 'Como Funciona' estão aparecendo lado a lado e ficando espremidos. Faça com que em mobile eles apareçam um abaixo do outro."

**Iteração 4 — Funcionalidade:**
"Adicione ao botão 'Quero minha aula experimental gratuita' no hero um link âncora que rola suavemente até o formulário de interesse."

Depois de 4-6 iterações assim, você tem um protótipo que pode mostrar para a professora Ana e ela vai entender exatamente como a página vai funcionar.

---

## Como lidar com especificações vagas do cliente

Na prática, clientes raramente chegam com especificações detalhadas. Eles dizem: "Quero um site para o meu negócio" ou "Precisa ser bonito e profissional."

Sua tarefa é transformar isso em especificação útil para a IA. Algumas perguntas que sempre funcionam:

- "Quais são os concorrentes que você admira? Posso analisar o estilo deles."
- "Você prefere algo mais clean/minimalista ou mais colorido e dinâmico?"
- "Qual a ação mais importante que você quer que o visitante faça?"
- "Quem é o seu cliente típico? Como ele chega até você hoje?"
- "Existe algum elemento que você definitivamente NÃO quer na página?"

Com essas respostas, você tem tudo que precisa para um bom prompt fundador.

---

## O loop de iteração profissional

Profissionais que usam essas ferramentas de forma eficiente seguem um loop específico. Não é caótico — é metódico.

```
ESPECIFICAR → GERAR → AVALIAR → PRIORIZAR PROBLEMAS → RESOLVER O MAIS IMPORTANTE → AVALIAR → ...
```

A chave é **priorizar problemas antes de começar a resolver.** Se você resolvesse cada problema na ordem em que aparece, pode acabar resolvendo detalhes visuais antes de corrigir problemas estruturais — que quando corrigidos vão mudar o visual de qualquer maneira.

Sempre resolva na ordem: estrutura → conteúdo → visual → funcionalidade.

---

## Erros comuns

**Erro 1: Fazer mudanças muito grandes de uma vez.**
O mecanismo: quando você pede para a IA fazer muitas mudanças em um único prompt, ela pode introduzir novos problemas enquanto resolve os anteriores. Prefira mudanças incrementais: uma ou duas alterações por mensagem.

**Erro 2: Não documentar o que estava bom.**
O mecanismo: depois de várias iterações, você pode não lembrar o que estava correto antes de uma mudança que piorou. Antes de solicitar uma mudança grande, escreva (para você mesmo) o que está funcionando e não deve mudar.

**Erro 3: Aceitar texto placeholder como conteúdo final.**
O mecanismo: "Lorem ipsum" e textos genéricos criados pela IA não comunicam o negócio real. Antes de qualquer apresentação para cliente, substitua por conteúdo real ou por conteúdo fictício mas específico e verossímil.

**Erro 4: Pular a avaliação estruturada e reagir impulsivamente.**
O mecanismo: quando o resultado não parece bom, a reação instintiva é pedir "melhore o design" ou "faça mais bonito." Isso é ineficiente. Force-se a identificar especificamente o que está errado antes de pedir qualquer mudança.

**Erro 5: Considerar o protótipo como produto final.**
O mecanismo: um protótipo funcional é excelente para validação, mas não é necessariamente o produto final. Imagens de qualidade, texto revisado por um redator, integração com formulários reais, domínio personalizado — esses são os passos que transformam o protótipo em produto.

---

## Exercício prático

Use o prompt que você desenvolveu nas aulas anteriores e execute o processo completo:

1. **Abra o Lovable** (lovable.dev) e crie um novo projeto
2. **Cole o prompt** que você desenvolveu
3. **Aguarde o resultado** — não interrompa durante a geração
4. **Avalie seguindo a sequência:** estrutura, conteúdo, visual mobile, funcionalidade
5. **Escreva 3 problemas específicos** que você identificou, em ordem de prioridade
6. **Resolva o problema mais importante** com um prompt cirúrgico
7. **Avalie o novo resultado** antes de partir para o próximo problema

O objetivo não é perfeição — é terminar o ciclo completo uma vez. A habilidade vem da prática repetida desse loop.

---

## Resumo

- Um protótipo funcional é uma versão navegável e interativa — você pula direto para isso ao usar ferramentas de IA, sem passar por wireframes ou mockups
- O processo completo tem 6 etapas: especificação, prompt fundador, avaliação, iteração estruturada, gestão de problemas, validação
- O prompt fundador define a arquitetura — invista 10-15 minutos nele antes de começar
- Itere na ordem correta: estrutura primeiro, depois conteúdo, depois visual, depois funcionalidade
- Prompts de iteração precisam ser cirúrgicos — específicos sobre o que deve mudar, sem destruir o que está funcionando
- Quando a IA gera algo errado: identifique a causa, reformule o pedido, ou volte para a versão anterior
- Transformar especificações vagas do cliente em prompts úteis é uma habilidade central — use perguntas específicas para extrair o que você precisa
