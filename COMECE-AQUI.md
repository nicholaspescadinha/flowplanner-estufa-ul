# FlowPlanner: comece aqui

Este é um app de gestão de obra que **já existe**, pronto para usar. O que falta é ligar ele ao
**seu** banco de dados e colocar no ar. Isso se faz com **dois prompts**, colados no seu agente de
IA: o **Claude Code** (app do Claude) ou o **Codex** (app do ChatGPT). O primeiro põe o app rodando
na sua tela em uns 20 minutos, para você ver o que tem em mãos antes de criar conta nenhuma. O
segundo cria o banco, liga o app, guarda o código no GitHub e te guia a publicar na Vercel. Você
não abre terminal e não digita comando: quem roda tudo é o agente, e você só aprova.

**Começou pelo Cowork e pelo Cursor?** Não refaça nada: o app, a pasta, o banco e o GitHub
continuam valendo. Instale o Claude Code ou o Codex, abra **esta mesma pasta** nele e escreva:
"leia o COMECE-AQUI.md, veja em que etapa eu parei e continue daí". Vídeo explicando:
https://youtu.be/xQXfMV7WJU4 (e, se você usa o ChatGPT: https://youtu.be/4v6YTZdMdaI).

**O caminho ideal é outro:** montar o seu próprio app do zero, desde o começo, pelo manual (no
portal, botão "Criar meu app do zero": https://portal.flowplanner.app.br/manual.html). É assim que
você aprende o processo inteiro e depois consegue mudar o que quiser. Use este app pronto se precisa
de algo funcionando já, ou como referência enquanto constrói o seu.

**Pode usar, não pode vender.** Você pode usar e adaptar este app nas suas obras e nas obras da
sua empresa. É proibido vender, revender, alugar, sublicenciar ou distribuir o app ou versões dele.
As regras estão no `LICENCA.txt`, nesta pasta.

**Tempo:** na primeira vez, reserve umas 3 horas, sem pressa. Perto de 1h30 é para preparar o
computador e as contas (uma vez só). O Prompt 1 leva uns 20 minutos e termina com o app na sua
tela. O Prompt 2 leva perto de 1h e, em umas 10 vezes, pede uma ação sua: um clique no site, uma
aprovação de comando ou um teste no app.

---

## Antes de colar os prompts

Se é a sua primeira vez, estes cinco passos preparam o computador e as contas. Uma vez só.

**1. Uma conta só: a do seu agente.** Escolha um dos dois e siga com ele até o fim. As outras três
contas (banco, cofre e publicação) ficam para depois do Prompt 1: não faz sentido criar conta de
banco de dados antes de ter visto o app na tela.

- **Claude Code** (o que eu uso): em [claude.ai](https://claude.ai), crie a conta e assine o plano
  **Pro** (uns US$ 20/mês; o grátis não tem o Claude Code). Pagamento em dólar: use um cartão que
  aceite compra internacional.
- **Codex** (se você já usa o ChatGPT): em [chatgpt.com](https://chatgpt.com), entre na sua conta.
  O Codex vem em todos os planos, mas para ligar e publicar o app inteiro o **Plus** é o que dá conta.

**2. Os programas (uns 30 minutos).**

- **O app do seu agente.** Claude Code: app do Claude, em [claude.ai/download](https://claude.ai/download),
  aba **Code**. Codex: app do ChatGPT, em [chatgpt.com/download](https://chatgpt.com/download),
  escolha o **Codex**. Tem que ser o app no computador, não o site.
- **Node.js**, em [nodejs.org](https://nodejs.org): clique na versão **LTS** e instale com next,
  next, finish.
- **Git**, em [git-scm.com](https://git-scm.com): Download for Windows e vá clicando Next até o fim,
  sem mudar nada. No Mac, depois, peça ao agente "instale o Git pra mim" e aceite a janela da Apple.

**Reinicie o computador depois de instalar.** Sem isso o Windows não enxerga o Node e o Git, e o
agente diz que "não encontrou o Node". Não precisa conferir nada aqui: o teste do passo 4 confere.

- Computador da empresa? Se o Windows pedir usuário e senha de administrador para instalar, monte
  num computador seu (ou peça à TI o Node.js LTS e o Git). Depois de pronto, o app abre em qualquer
  navegador, inclusive no computador da empresa e no celular.

**3. A pasta.** Este app tem que morar numa pasta **local**, sem OneDrive, Google Drive ou Dropbox.
O caminho certo é este, e dentro dele, logo de cara, tem que estar este COMECE-AQUI.md:

```
%userprofile%\Projetos\FlowPlanner
```

Como criar: aperte juntas a tecla do Windows e a tecla R, cole este comando na janelinha Executar e
aperte Enter. Abre a pasta FlowPlanner (vazia, na primeira vez):

```
cmd /c mkdir "%userprofile%\Projetos\FlowPlanner" & explorer "%userprofile%\Projetos\FlowPlanner"
```

Não precisa extrair o ZIP: no teste da oficina (item 4), o agente tira os arquivos da pasta
Downloads e põe aqui. Se você está lendo este arquivo dentro de uma pasta a mais no meio (por
exemplo `FlowPlanner\flowplanner-app\COMECE-AQUI.md`), peça ao agente: "os arquivos do app estão
numa pasta a mais no meio; traga eles para a pasta FlowPlanner".

Se o seu nome de usuário do Windows tiver espaço ou acento, tudo bem. O que não pode é você criar
pasta nova com espaço ou acento. Cuidado com a pasta `Documentos` e com a Área de trabalho: no
Windows elas costumam ser o OneDrive sem você ter pedido. Clique na barra de endereço; se aparecer
OneDrive no caminho, saia de lá. No Mac, a pasta fica em Início/Projetos, fora do iCloud.

**4. A pasta no seu agente.** Só isso: conector nenhum por enquanto, eles entram depois do Prompt 1.

- **Escolha a pasta.** Claude Code: na aba Code, antes da primeira mensagem, clique no seletor de
  pasta na caixa de mensagem e escolha a pasta FlowPlanner. Codex: abra uma pasta e escolha a mesma.
  Toda conversa nova começa escolhendo a pasta de novo.
- **Licença.** O agente pede licença antes de rodar comando, baixar da internet ou enviar pro
  GitHub. Leia a primeira linha e aprove. No Claude Code, deixe o modo em **Accept edits**; no
  Codex, no que já vem, **Ask for approval**. Recuse só se o pedido falar em mexer fora da pasta ou
  apagar algo que você não pediu.
- **Modelo:** o mais forte (no Claude, o **Opus**).
- **Teste da oficina (e o app entra na pasta).** Cole a mensagem abaixo. Ele pede licença para ler
  a pasta Downloads: aqui pode aprovar. Deu certo quando ele mostrou o COMECE-AQUI.md, o
  package.json e as pastas public e src dentro da pasta FlowPlanner, e respondeu duas versões. Falou
  de outra pasta: a pasta não foi escolhida. Não achou o ZIP: baixe de novo e conte a ele onde o
  navegador salvou. Não achou o Node ou o Git: faltou reiniciar.

```text
OFICINA. Faça nesta ordem e me responda em linhas curtas:
1. Me diga o caminho completo desta pasta. Se ele passar por OneDrive, Google Drive, Dropbox ou iCloud, pare aqui e me avise: o app não pode morar em pasta que sincroniza.
2. Na minha pasta Downloads está o flowplanner-app.zip. Se houver mais de um (por exemplo "flowplanner-app (1).zip"), use o de data mais recente. Extraia ele aqui nesta pasta (no Windows, com tar -xf), de um jeito que o COMECE-AQUI.md, o package.json e as pastas public e src fiquem logo aqui, sem outra pasta no meio. Não apague nada em Downloads.
   Se não houver .zip, procure em Downloads uma pasta flowplanner-app (o Mac às vezes abre o zip sozinho) e copie o que tem dentro dela para cá.
   Se os arquivos do app já estiverem aqui, mas dentro de uma pasta a mais no meio (de uma tentativa anterior), traga eles para cá.
3. Me mostre o que ficou nesta pasta e me diga qual versão do Node e qual versão do Git estão instaladas neste computador.
```

**Instale a skill `criar-app-v3`.** Skill é um especialista que o agente chama pelo nome. Aqui você
não vai construir nada do zero, o app já existe, mas é ela que ensina ao agente as regras da casa:
como rodar o npm no Windows sem tropeçar, como guardar no GitHub sem apagar nada, o que fazer quando
algo trava. Baixe o .zip na Caixa de Ferramentas da sua estante e deixe fechado na pasta Downloads
(já tinha baixado antes? baixe de novo). Depois cole no agente:

```text
Acabei de baixar a skill criar-app-v3 na minha pasta Downloads, num arquivo .zip.
Atenção: pode ter mais de um arquivo dela, de downloads antigos (por exemplo criar-app-v3.zip e "criar-app-v3 (1).zip"). Use SEMPRE o de data mais recente e me diga a data do que você escolheu. Se existir uma skill antiga chamada criar-app-v2, apague ela: a criar-app-v3 substitui e continua os projetos começados com a v2.
Instale como skill minha, que valha em qualquer projeto, no lugar onde você procura as suas skills, substituindo qualquer versão que já esteja instalada. Confira que os arquivos ficaram no lugar certo e me avise quando terminar.
```

Ele pede licença para mexer fora da pasta (Downloads e a pasta das skills): aqui pode aprovar.
Confira numa conversa nova: digite `/` no Claude Code ou `$` no Codex, e a `criar-app-v3` tem que
aparecer na lista.

**5. A sua logo (opcional).** Quer a logo da sua empresa no ícone do app? Antes de colar o prompt,
salve a logo, de preferência **quadrada** e em **PNG**, com o nome `minha-logo.png` (JPG também serve,
com o nome `minha-logo.jpg`; se não for quadrada, o comando centraliza num fundo branco), dentro
da pasta `public` desta pasta. No segundo prompt o agente roda `npm run icones`, que faz os
ícones com ela. Sem logo, fica o ícone FP. Com ou sem logo, o nome que você puser em Empresa aparece
sozinho na aba do navegador e no atalho do celular.

---

## Preencha estas cinco linhas

Troque o que está entre colchetes no bloco "Meus dados" do prompt. Os colchetes só aparecem nessas
cinco linhas. Dica: cole o prompt no Bloco de Notas, troque as cinco linhas e só então copie tudo
para o seu agente.

| campo | o que colocar | exemplo |
|---|---|---|
| NOME_DA_EMPRESA | como o app vai se chamar na tela de entrada, nos PDFs, na aba do navegador e no atalho do celular | `Construtora Silva` |
| NOME_DA_OBRA | a obra que você vai gerenciar primeiro | `Residencial Aurora` |
| DOMINIO_DO_EMAIL | o que vem depois do @ nos e-mails da sua empresa (se usa gmail ou hotmail, ponha esse) | `silva.eng.br` |
| INICIO_DA_OBRA | o dia em que a obra começou, para o app contar a semana da obra (opcional) | `16/03/2026` |
| SEU_EMAIL | o e-mail com que **você** vai entrar no app | `andre@silva.eng.br` |

---

## Prompt 1: veja o app na sua tela

Este primeiro prompt não cria conta, não mexe em banco e não publica nada. Ele só põe o app rodando
no seu computador, já com o nome da sua empresa e da sua obra, para você ver com os próprios olhos o
que baixou. Uns 20 minutos, e a maior parte é o computador instalando sozinho.

Copie daqui até o fim do bloco, troque os campos entre colchetes, cole no seu agente.

```text
Você vai me mostrar na tela o app FlowPlanner que está nesta pasta, com a minha cara,
rodando no meu computador. Só isso. Nada de banco de dados, nada de GitHub, nada de
publicar: isso fica para o segundo prompt. Ele já está pronto e testado: NÃO reescreva
nada dele, não "melhore" e não troque biblioteca. Siga as etapas na ordem e só passe
para a próxima quando o "Pronto quando" da atual estiver comprovado: visto, não presumido.

Meus dados:
- Empresa: [NOME_DA_EMPRESA]
- Obra: [NOME_DA_OBRA]
- Começo da obra: [INICIO_DA_OBRA]
- Domínio de e-mail: [DOMINIO_DO_EMAIL]

Regras que valem do início ao fim:
- Quem roda os comandos é você, aqui, nesta pasta. Eu não abro terminal e não digito
  comando nenhum. Antes de cada comando, me diga em uma linha o que ele faz: eu aprovo
  quando você pedir licença.
- Se a skill criar-app-v3 (ou a antiga criar-app-v2) estiver instalada, siga as regras dela sobre Windows e
  comandos, mas as etapas são estas daqui. Não comece o roteiro de construção dela:
  o app já existe.
- No Windows, se o npm recusar com uma mensagem sobre "execução de scripts" ou npm.ps1,
  use npm.cmd no lugar de npm (e npx.cmd no lugar de npx) daqui pra frente. Nunca me
  mande mexer em configuração do Windows.
- Me diga sempre onde cada coisa acontece: "aqui na conversa" ou "no navegador".
- Quando precisar de uma ação minha, peça uma de cada vez e espere eu responder.

ETAPA 0: Reconheça a pasta
Leia: COMECE-AQUI.md, src/marca.js, .env.example, package.json.
Confira que o Node está instalado (node -v).
Me conte em 5 linhas o que o app faz e o que você vai fazer agora. Não mude nada ainda.
Se você não estiver enxergando os arquivos desta pasta, pare e me diga: é sinal de que
a conversa foi aberta sem a pasta FlowPlanner escolhida, e nada daqui para frente vai
funcionar. Se o Node não for encontrado, me diga para reiniciar o computador e abrir
uma conversa nova: ele só aparece depois do reinício.
Pronto quando: você me listou os arquivos que leu e a versão do Node.

ETAPA 1: Deixe o app com a minha cara
Edite src/marca.js: nome = empresa, obra = obra, dominioEmail = domínio de e-mail,
inicioObra = o dia em que a obra começou, no formato AAAA-MM-DD (se eu não souber ou
não quiser, deixe vazio: aí o app não mostra o número da semana da obra).
Só esse arquivo. O nome da empresa passa a aparecer sozinho na tela de entrada, nos PDFs,
na aba do navegador e no atalho do celular.
Pronto quando: você me mostra o marca.js editado.

ETAPA 2: Ligue o modo demonstração
Crie o arquivo .env.local na raiz da pasta com exatamente estas três linhas:
  VITE_DEMO=1
  VITE_SUPABASE_URL=https://demo.invalid
  VITE_SUPABASE_ANON_KEY=demo
Me explique em duas linhas o que isso faz: o app roda inteiro com dados de mentira, sem
banco nenhum e sem pedir senha, só para eu ver as telas. No segundo prompt esse arquivo é
trocado pelos dados do meu banco de verdade.
Confirme que .env.local está no .gitignore.
Pronto quando: você me mostra o conteúdo do arquivo.

ETAPA 3: Ligue o app
1. Rode npm install. Me avise antes: "leva de 1 a 5 minutos e baixa as peças do app da
   internet; vou pedir licença para isso". No fim pode aparecer a palavra
   vulnerabilities: é normal, são ferramentas de desenvolvimento. Não rode
   npm audit fix.
2. Rode npm run dev em segundo plano, de um jeito que o app continue ligado enquanto a
   gente conversa. Confira você mesmo que o endereço responde (normalmente
   http://localhost:5173) e me diga o endereço.
   Se a sua ferramenta não conseguir deixar o app ligado em segundo plano (ele desliga
   quando o comando termina), me avise e me guie, um clique por vez, a rodar npm run dev
   no terminal que existe dentro do próprio app em que estamos conversando.
Me explique em uma frase: o app fica ligado enquanto esta conversa estiver aberta; se eu
fechar e quiser ver de novo, é só abrir uma conversa na mesma pasta e dizer "liga o app".
Pronto quando: você confirmou que o endereço responde e me passou o endereço.

ETAPA 4: Passeie pelo app
Me peça para abrir o endereço no navegador. O app abre direto, sem pedir senha: no modo
demonstração não existe login.
Me peça, um de cada vez, e espere eu responder:
 (1) olhar o topo da tela Início e confirmar que aparece o nome da minha obra;
 (2) clicar em Pendências e ver a lista;
 (3) clicar em Cronograma e em Efetivo;
 (4) clicar em Relatórios e abrir um relatório.
Depois me diga, em linguagem simples, três coisas:
 - tudo que eu vi é de mentira e some quando eu desligar: nada foi salvo;
 - este app roda só no meu computador, ninguém mais consegue abrir;
 - para ele virar o app da minha obra de verdade, com os meus dados salvos e aberto no
   celular da equipe, eu colo o segundo prompt, o de ligar no banco e publicar.
Pronto quando: eu vi o nome da minha obra no topo e naveguei pelas quatro telas.
```

**Tudo que você vai ver aqui é de mentira.** O app abre sem pedir senha e mostra obra, efetivo e
pendências inventados, só para você conhecer as telas. Nada é salvo e ninguém além de você consegue
abrir. É de propósito: o banco de verdade é o próximo passo.

### O que vai acontecer

Você não digita nada disto: quem roda é o agente, e você só aprova quando ele pedir licença. Está
aqui para você reconhecer o que aparecer na tela.

**1. Ele instala as peças do app** (`npm install`). Uma vez só, de 1 a 5 minutos. Ele pede licença
para baixar da internet: aprove. No fim pode aparecer a palavra *vulnerabilities*: é normal.

**2. Ele liga o app** (`npm run dev`). O app fica ligado em segundo plano enquanto a conversa estiver
aberta. Fechou e quer ver de novo outro dia? Abra uma conversa na mesma pasta e diga "liga o app".

**E aí está o seu app.** O agente te passa um endereço parecido com `http://localhost:5173`. Abra no
navegador. O app abre direto, sem pedir senha, já com o nome da sua obra no topo. Passeie por
Pendências, Cronograma, Efetivo e Relatórios.

---

## Agora sim: as contas do banco e da publicação

Você já viu o app funcionando. Agora ele precisa de um lugar para guardar os dados de verdade, de um
cofre para o código e de um endereço na internet. Três contas, todas grátis, uns 20 minutos. Nesta
ordem, porque o Supabase e a Vercel entram pela conta do GitHub.

| conta | pra que serve | custo |
|---|---|---|
| [github.com](https://github.com) | o cofre do código, privado | grátis |
| [supabase.com](https://supabase.com) | banco de dados, login e fotos | grátis |
| [vercel.com](https://vercel.com) | coloca o app no ar | grátis |

- **GitHub:** ele pede para resolver um quebra-cabeça e manda um código para o seu e-mail. É normal.
  Anote o seu nome de usuário e o e-mail com que criou a conta: o agente vai perguntar o e-mail.
- **Supabase:** clique em Continue with GitHub. Se ele pedir para criar uma organização, crie (o
  seu nome ou o da empresa, plano Free). Se oferecer criar um **projeto**, não crie: quem cria é o
  prompt, com o nome e a região certos.
- **Vercel:** clique em **Continue with GitHub**. Não pule: é isso que deixa a Vercel ver o seu
  código e publicar sozinha. Se perguntar o tipo de uso, escolha Hobby, o grátis.

**Ligue os dois conectores.** Conector é o que deixa o agente operar o Supabase e a Vercel por você.
Uma vez só, vale para sempre.

- **Claude Code:** no app do Claude, **Configurações, Conectores** (ou o + ao lado da caixa de
  mensagem, Conectores). Procure **Supabase**, Conectar, autorize com a sua conta. Repita com a
  **Vercel**.
- **Codex:** cole no Codex e aprove quando ele pedir licença; no navegador, autorize os dois:

```text
Adicione dois servidores MCP nas suas configurações, pra valer em todos os meus projetos:
- supabase, com o endereço https://mcp.supabase.com/mcp
- vercel, com o endereço https://mcp.vercel.com
Depois faça o login em cada um. Vai abrir o navegador pra eu autorizar: me avise antes de cada um.
```

Confira numa **conversa nova** (conector novo só aparece nela): "Liste os meus projetos do Supabase e
os meus projetos da Vercel". Listou, mesmo vazio? Está ligado. Disse que não tem acesso? No Claude
Code, Conectores, clique no conector, Desconectar e Conectar de novo; no Codex, peça "faça o login de
novo no servidor supabase". O GitHub **não** precisa de conector: o agente envia o código pelo Git.

---

## Prompt 2: ligue no seu banco e publique

Agora sim. Este cria o seu banco de dados, faz o seu login, troca os dados de mentira pelos de
verdade, guarda o código no GitHub e põe o app no ar num link que abre no celular da equipe. Perto
de uma hora, e a parte mais longa é sua: testar e clicar nos sites quando ele pedir.

**Cole numa conversa NOVA**, escolhendo de novo a pasta FlowPlanner. Este prompt se vira sozinho, não
precisa do que foi conversado antes. Conversa comprida é o que faz a IA começar a esquecer.

Se precisar parar, pare no fim de uma etapa e depois escreva na mesma conversa: "continue da ETAPA X".

```text
Você vai ligar ao MEU banco de dados o app FlowPlanner que está nesta pasta, me deixar
entrar nele, guardar o código no GitHub e me guiar a publicar. Eu já rodei o primeiro
prompt: o app já está com a minha cara e eu já o vi rodando no meu computador, com dados
de mentira. Agora é para valer. Ele já está pronto e testado: NÃO reescreva nada dele.
Siga as etapas na ordem e só passe para a próxima quando o "Pronto quando" da atual
estiver comprovado: visto, não presumido.

Meus dados:
- Empresa: [NOME_DA_EMPRESA]
- Obra: [NOME_DA_OBRA]
- Meu e-mail: [SEU_EMAIL]

Regras que valem do início ao fim:
- Quem roda os comandos (npm e git) é você, aqui, nesta pasta. Eu não abro terminal e
  não digito comando nenhum. Antes de cada comando, me diga em uma linha o que ele faz:
  eu aprovo quando você pedir licença.
- Se a skill criar-app-v3 (ou a antiga criar-app-v2) estiver instalada, siga as regras dela sobre Windows, git e
  segurança, mas as etapas são estas daqui. Não comece o roteiro de construção dela:
  o app já existe.
- No Windows, se o npm recusar com uma mensagem sobre "execução de scripts" ou npm.ps1,
  use npm.cmd no lugar de npm (e npx.cmd no lugar de npx) daqui pra frente. Nunca me
  mande mexer em configuração do Windows.
- O GitHub é sempre pelo git, nesta pasta, mesmo que apareça um conector do GitHub.
  Nunca use git push --force.
- Banco e edge function: use as ferramentas do Supabase (o conector). Não me mande abrir
  o SQL Editor e colar coisa na mão.
- A publicação eu faço uma vez no site da Vercel, guiado por você. As ferramentas da
  Vercel (o conector) você usa só para conferir.
- O arquivo banco.sql é a fonte do banco. Não crie tabela, coluna ou regra de acesso
  por conta própria, nem "melhore" o que está lá.
- Nunca crie usuário por SQL. Login novo nasce no site do Supabase (o meu, na ETAPA 4)
  ou no Painel de admin do app.
- A chave "service_role" do Supabase nunca vai para arquivo nenhum desta pasta e nunca
  aparece aqui na conversa.
- Quando precisar de uma ação minha, peça uma de cada vez e espere eu responder.
- Me diga sempre onde cada coisa acontece: "aqui na conversa", "no navegador, no site
  do Supabase", "no navegador, no site da Vercel".

ETAPA 0: Confira onde eu parei
Leia: COMECE-AQUI.md, banco.sql, supabase/functions/admin-usuarios/index.ts,
src/marca.js, .env.local, .env.example, package.json, .gitignore.
Confira três coisas e me diga o resultado:
 (a) o src/marca.js já tem o nome da minha empresa e da minha obra? Se ainda estiver
     escrito FlowPlanner e "Minha obra", eu pulei o primeiro prompt: me avise e
     preencha agora, com os dados do bloco Meus dados;
 (b) existe um .env.local com VITE_DEMO=1? Se existir, é do primeiro prompt e vai ser
     substituído na ETAPA 3. Se não existir nenhum .env.local, tudo bem também;
 (c) você enxerga as ferramentas do Supabase e da Vercel? Se faltar alguma, pare e me
     diga qual: eu ligo o conector (é o passo 7 da página do app pronto) e abro uma
     conversa nova.
Me conte em 5 linhas o que você vai fazer agora. Não mude nada ainda.
Pronto quando: você me disse como encontrou o marca.js, o .env.local e os conectores.

ETAPA 1: O banco de dados
1. Liste os meus projetos do Supabase e me mostre a lista: nome, região e situação.
   - Se existir um chamado "flowplanner", use esse. Se ele estiver pausado, não
     restaure: me peça para clicar em Restore no site e espere. Se ele já tiver
     tabelas, me mostre quais: se forem as do FlowPlanner (de uma tentativa minha
     anterior), pode seguir, porque o banco.sql roda de novo sem apagar nada; se
     forem outras, pare e me pergunte.
   - Qualquer outro projeto: NÃO use, NÃO restaure e NÃO aplique nada nele. Ele pode
     ser de outro sistema meu.
   - Se não existir um "flowplanner", crie um com esse nome, na região de São Paulo
     (sa-east-1), no plano gratuito. Se o Supabase recusar porque o plano gratuito já
     tem 2 projetos ativos, ou pedir para aceitar algum custo, pare e me explique. Eu
     decido no site o que fazer. Nunca aceite custo sem me perguntar.
   Me avise que criar demora um ou dois minutos e espere ficar pronto.
2. Aplique o arquivo banco.sql INTEIRO como uma migration chamada "banco_inicial".
   Leia o arquivo e envie o conteúdo exatamente como está, sem resumir nem cortar nada.
   Se der um erro com as palavras "does not exist", envie de novo o arquivo inteiro
   com esta única linha na frente:
     set local check_function_bodies = off;
   Essa linha não cria nem muda nada no banco: só deixa a conferência das funções
   para depois.
   Se der qualquer outro erro, pare e me mostre a mensagem inteira. Não divida o
   arquivo e não conserte o banco.sql.
3. Confira: liste as tabelas, tem que haver 27. E rode
   "select count(*) from public.relatorio_semanal_config": tem que dar 1.
Pronto quando: as 27 tabelas aparecem e a contagem dá 1.

ETAPA 2: O Painel de admin (edge function)
Publique a edge function "admin-usuarios" com o arquivo
supabase/functions/admin-usuarios/index.ts desta pasta, com verificação de JWT ligada.
Depois liste as edge functions e me mostre que ela está ACTIVE.
Sem ela o app funciona, mas o Painel de admin, onde eu crio os logins da equipe, não.
Pronto quando: a admin-usuarios aparece ACTIVE.

ETAPA 3: Troque a demonstração pelo banco de verdade
Pegue a URL do projeto e a chave pública "anon", a que começa com eyJ. Não use a
service_role. Reescreva o arquivo .env.local na raiz da pasta com exatamente estas duas
linhas, e só elas:
  VITE_SUPABASE_URL=<a url>
  VITE_SUPABASE_ANON_KEY=<a chave anon>
A linha VITE_DEMO=1 tem que SUMIR. Enquanto ela existir, o app continua mostrando dados
de mentira e nunca fala com o banco: é o engano número um aqui.
Confirme que .env.local está no .gitignore.
Depois religue o app, você mesmo: um app que já estava ligado continua com o arquivo
antigo na memória. Se houver um npm run dev ligado por você, desligue e ligue de novo,
em segundo plano. Se houver um ligado de antes (de outra conversa) que você não
consegue desligar, ligue um novo assim mesmo e me diga o endereço que ele mostrar (pode
vir 5174 em vez de 5173): é esse que eu uso daqui pra frente.
Pronto quando: você me mostra o conteúdo do arquivo (a chave anon pode aparecer, ela
não é segredo) e me passa o endereço do app religado.

ETAPA 4: Meu login e duas chaves desligadas
Você não consegue criar o meu usuário por aqui: eu faço no site e você termina.
1. Me guie, uma tela por vez: "No navegador, entre em supabase.com e abra o projeto
   flowplanner. No menu da esquerda, passe o mouse nos ícones até achar
   Authentication e clique. Clique em Users, depois no botão Add user, depois em
   Create new user. E-mail: o seu, o mesmo do bloco Meus dados. Senha: uma que você
   vá lembrar, com pelo menos 8 letras e números. Marque a caixinha Auto Confirm User.
   Clique em Create user e volte aqui escrevendo criei."
2. Quando eu disser "criei", pergunte o meu primeiro nome e rode:
     update public.profiles
        set is_admin = true, role = 'engenheiro', nome = '<meu primeiro nome>'
      where id = (select id from auth.users where lower(email) = lower('<meu e-mail>'));
   e confira com "select nome, role, is_admin from public.profiles".
   Me explique: todo login novo nasce como visitante, que só olha. Quem dá o papel
   (engenheiro ou mestre) sou eu, pelo Painel de admin do app.
3. Agora me guie a desligar duas chaves no site, uma de cada vez: "Ainda em
   Authentication, no menu da esquerda, clique em Sign In / Providers.
   (a) Desligue a chave Allow new users to sign up e clique em Save. Assim ninguém
       de fora cria conta no seu app.
   (b) Na mesma tela, clique em Email. A primeira chave, Enable Email provider, fica
       LIGADA: sem ela ninguém entra no app. Desligue só a chave Confirm email e
       clique em Save. Sem isso, quem você cadastrar pode ficar travado com 'e-mail
       não confirmado', e o app não tem tela para confirmar."
   Confira as três: leia a configuração pública do login (GET em
   <a url do projeto>/auth/v1/settings, com o cabeçalho apikey = a chave anon) e veja
   "disable_signup": true, "mailer_autoconfirm": true e, dentro de "external",
   "email": true. Se você não conseguir ler por aqui, me peça um print da tela e
   confira nele.
Se mais tarde o app disser que o meu e-mail não foi confirmado, é porque a caixinha
Auto Confirm User ficou desmarcada. Aí rode:
  update auth.users set email_confirmed_at = now()
   where lower(email) = lower('<meu e-mail>') and email_confirmed_at is null;
Pronto quando: aparece a minha linha com o meu nome, role engenheiro e is_admin true,
e a leitura mostra "disable_signup": true, "mailer_autoconfirm": true e
"external": {"email": true}.

ETAPA 5: A minha logo, e o teste de verdade
1. Veja se existe o arquivo public/minha-logo.png (ou public/minha-logo.jpg):
   - se existir, rode npm run icones. Ele faz os ícones do app com a minha logo. Se der
     erro, me diga que o app funciona igual, com o ícone FP, e siga;
   - se existir um arquivo parecido (minha-logo.png.png, logo.png), me pergunte se é a
     minha logo e, se eu disser que sim, renomeie você mesmo e rode o comando;
   - se não existir nenhum, tudo bem: o app fica com o ícone FP. Não pergunte de novo.
2. Agora o app fala com o banco, e por isso ele vai PEDIR SENHA, coisa que no primeiro
   prompt não acontecia. Me avise disso antes.
   Me peça, um de cada vez, e espere eu responder:
    (1) abrir no navegador o endereço que você me passou na ETAPA 3 e entrar com o meu
        e-mail completo e a senha que eu criei na ETAPA 4;
    (2) clicar em Pendências, + Nova, escrever um problema qualquer, Próximo até o fim e
        Criar pendência;
    (3) apertar F5 e ver se a pendência continua lá;
    (4) clicar na bolinha com a minha inicial (no computador, no pé da barra da
        esquerda; no celular, no alto da tela Início) e depois em Painel de admin: tem
        que aparecer a lista Usuários com o meu e-mail.
   Se eu disser que continuo vendo os dados de mentira, ou que ele não pediu senha, é o
   VITE_DEMO ou o app que não foi religado: confira o .env.local e religue o app.
Se algo falhar, eu te colo o erro e você conserta, sem mexer no banco.sql.
Pronto quando: entrei, a pendência sobreviveu ao F5 e o Painel de admin mostrou o
meu e-mail.

ETAPA 6: Guardar no GitHub
Quem roda o git é você, aqui. Eu só crio o repositório no site e autorizo o login.
1. Antes de tudo, veja se já existe uma pasta .git aqui (de uma tentativa minha
   anterior). Se existir, rode git remote -v e git status, me mostre o endereço e me
   pergunte se é o meu repositório do FlowPlanner. Se for, pule para o passo 5.
2. Me guie a criar o repositório, uma tela por vez: "No navegador, em github.com,
   clique no + no canto de cima, à direita, depois em New repository. Em Repository
   name escreva flowplanner-" seguido do nome curto da obra, em minúsculas, sem
   espaço e sem acento (ex.: flowplanner-aurora). "Marque Private. Não marque README,
   .gitignore nem license: o repositório tem que nascer vazio. Clique em Create
   repository e cole aqui o endereço da página que abrir." Se o GitHub disser que o
   nome já existe, sugira o mesmo nome terminado em -2.
3. Me pergunte com que e-mail eu criei a conta do GitHub. É ESSE que vai como autor,
   mesmo que seja diferente do e-mail do app: com outro e-mail, a Vercel bloqueia a
   publicação. Veja o que já está configurado (git config --global user.email). Se
   estiver vazio, configure o meu nome e esse e-mail. Se já existir e for outro, me
   pergunte qual usar antes de trocar.
4. Faça o primeiro envio: git init -b main, git add ., git commit -m "FlowPlanner da
   obra <obra>", git remote add origin <o endereço que colei>.git.
   Antes do push, a trava: rode git ls-files .env.local. Tem que voltar vazio. Se
   aparecer o nome do arquivo, pare: as chaves subiriam. Tire do índice
   (git rm --cached .env.local), confira o .gitignore e só então siga.
   Me avise antes do push: "vai abrir uma janela do GitHub no seu navegador pedindo
   para entrar. Entre com a sua conta e clique em Authorize. É só desta vez." Então
   rode git push -u origin main. Se ele ficar parado esperando, é essa janela.
5. Confira com git status que está em dia com origin/main.
Pronto quando: eu abro o endereço do repositório, vejo as pastas src, public e
supabase, e você me confirmou que o git ls-files .env.local voltou vazio.

ETAPA 7: Publicar na Vercel
Quem publica sou eu, uma vez só, no site da Vercel. Depois disso cada "sobe pro
GitHub" publica sozinho. Você me guia e confere pelas ferramentas da Vercel.
1. O vercel.json já existe na raiz e diz à Vercel como montar o app. Não altere.
2. Me mostre, num bloco fácil de copiar, as duas variáveis com os valores do
   .env.local, uma por linha:
     VITE_SUPABASE_URL=<a url>
     VITE_SUPABASE_ANON_KEY=<a chave anon>
   (A chave anon é pública, pode aparecer aqui.)
3. Me guie, uma tela por vez, no navegador, em vercel.com:
   - Add New, depois Project.
   - Na lista Import Git Repository, ache o repositório flowplanner-... que criei na
     ETAPA 6 e clique em Import. Se ele não aparecer: clique em Adjust GitHub App
     Permissions (ou Install), escolha a minha conta, marque All repositories (ou só o
     flowplanner-...), Save, e volte.
   - Na tela Configure Project, abra Environment Variables. Cole o bloco inteiro no
     primeiro campo (Key): a Vercel separa as duas sozinha. Se não separar, cadastre
     uma por vez, com o nome no primeiro campo e o valor no segundo. Confira que
     ficaram as duas. Não mexa em Framework Preset nem em Root Directory: o
     vercel.json já cuida disso.
   - Clique em Deploy e espere uns 2 minutos, até aparecer a tela de parabéns.
4. Com as ferramentas da Vercel, confira que o projeto existe, que a última publicação
   está READY e que ela está ligada ao repositório. Se der erro, leia o log da
   publicação e me diga o que fazer, sem mexer no banco.sql. Se ela aparecer como
   Blocked (pelas ferramentas vem só o estado BLOCKED e um link de ajuda sobre
   colaboração; no site pode vir escrito que não achou conta do GitHub com o e-mail
   do autor do commit), o e-mail do git não é o da minha conta do GitHub. Me pergunte
   de novo o e-mail da conta do GitHub, acerte o user.email, faça um commit vazio
   (git commit --allow-empty -m "publicar de novo") e rode git push. A Vercel publica
   sozinha esse commit novo. Confira de novo pelas ferramentas.
5. Me dê SÓ o link curto de produção, no formato https://<nome-do-projeto>.vercel.app.
   NUNCA me dê o link comprido, com letras e números no meio: esse pede login da
   Vercel e o meu mestre de obras não consegue abrir.
6. Me peça para abrir o link curto no celular e entrar com o meu login.
Pronto quando: o link curto abre no celular, eu entro, e a pendência que criei está lá.

ETAPA 8: Fechamento
1. Rode a verificação de segurança do Supabase (advisors) e me diga, em linguagem
   simples, se apareceu algo que eu precise fazer. Avisos sobre funções "security
   definer" e sobre "leaked password protection" são conhecidos e não impedem o uso.
2. Rode esta conferência:
     select has_column_privilege('authenticated','public.profiles','role','UPDATE') as muda_papel,
            has_column_privilege('authenticated','public.profiles','is_admin','UPDATE') as vira_admin;
   Tem que dar false nas duas colunas, muda_papel e vira_admin: ninguém logado consegue mudar o próprio papel nem se
   fazer administrador. Se der true em qualquer um, pare e me avise: o banco.sql
   desta pasta não é a versão certa.
3. Me entregue, numa lista curta: o link curto do app, o link do GitHub, o nome do
   projeto no Supabase e as três frases que eu vou usar daqui para frente:
   - "sobe pro GitHub": você mesmo roda o git add, o commit e o push, aqui. A Vercel
     publica sozinha em um ou dois minutos;
   - "cria um usuário para o João, mestre": você me guia, ou eu mesmo faço no Painel
     de admin do app, botão + Novo;
   - "o que mudou hoje?": numa conversa nova, na mesma pasta, você relê a pasta e me
     situa antes de mexer em qualquer coisa.
4. Me lembre: se o app ficar uma semana sem uso, o Supabase grátis pausa o projeto. É
   só entrar em supabase.com, abrir o projeto e clicar em Restore.
Pronto quando: você me entregou a lista e a conferência deu false | false.
```

---

## Deu certo quando

- O link curto da Vercel (o que termina em .vercel.app) abre no celular e você entra com o seu e-mail.
- Uma pendência criada no celular aparece no computador.
- No site do Supabase, no seu projeto, clique em Table Editor no menu da esquerda: a lista tem 27
  tabelas.
- No GitHub, o repositório mostra o código e **não** mostra `.env.local`.
- No site do Supabase, em Authentication, Sign In / Providers: "Allow new users to sign up" está
  desligado e, dentro de Email, "Confirm email" também.

De brinde: o efetivo que o mestre marca no canteiro aparece sozinho na tela do escritório.

## Cuidados com a equipe e as fotos

- **Dê login só a quem você confia e troque a senha de quem sair da equipe** (no Painel de admin):
  quem tem login de mestre ou engenheiro pode apagar registros.
- **Fotos:** quem recebe o link de uma foto consegue ver, como foto mandada no WhatsApp. O resto do
  app só abre com login.
- Todo login novo nasce como visitante, que só olha. Quem dá o papel (mestre ou engenheiro) é você,
  no Painel de admin: bolinha com a sua inicial, Painel de admin, + Novo.

## Se travar

Cole o erro **inteiro** no seu agente e diga em que etapa estava. Não tente consertar por conta: o
app foi testado, e o erro quase sempre é de chave, variável ou pasta, coisas que o agente resolve em
um minuto vendo a mensagem.

- **O agente diz que o `npm` "não pode ser carregado" ou fala em `npm.ps1`?** É o Windows bloqueando
  um tipo de script, e o conserto não mexe em nada no computador: basta usar o `npm.cmd`. Os prompts
  já avisam o agente. Se ele empacar, cole: "use npm.cmd no lugar de npm, e npx.cmd no lugar de npx,
  daqui pra frente neste projeto". **Não mexa em configuração do Windows** por causa disso.
- **O app mostra obra e gente que você nunca cadastrou?** São os dados de mentira do Prompt 1: ficou
  a linha `VITE_DEMO=1` no `.env.local`, ou o app não foi religado. Outro sinal: o app abre sem pedir
  senha. Escreva: "o app ainda está em modo demonstração, confira o .env.local e religue o app".
- **O agente não encontrou o Node ou o Git?** Quase sempre é o reinício que faltou. Reinicie e abra
  uma conversa nova, na mesma pasta.
- **Apareceu aviso de limite de uso?** Numa sessão longa, o plano pode bater no limite. Espere o
  horário que ele mostra e escreva, na mesma conversa: "continue de onde parou".
- **Funcionava e parou?** Primeiro, veja se o app ficou uma semana sem uso: no plano grátis o
  Supabase pausa o projeto. Entre em supabase.com, abra o projeto e clique em Restore. Se não for
  isso, abra uma conversa nova, na mesma pasta, e escreva: "o app parou de funcionar; confira o
  .env.local, o projeto do Supabase e a Vercel e me diga o que mudou".
- **Alguém travou em "e-mail não confirmado"?** No site do Supabase, em Authentication, Sign In /
  Providers, Email: a chave "Confirm email" tem que estar desligada. Depois escreva no agente: "o
  login de fulano@empresa.com diz que o e-mail não foi confirmado".
- **A Vercel mostra "Blocked" e não publica?** Quase sempre é o e-mail do git diferente do e-mail da
  sua conta do GitHub. Escreva: "a Vercel bloqueou a publicação". Ele acerta o e-mail, faz um envio
  novo e, em um ou dois minutos, a Vercel publica sozinha.
- **Subiu pro GitHub e a Vercel não publicou?** Acontece de vez em quando no plano grátis: o código
  chega no GitHub, mas a Vercel não acorda. No site da Vercel, abra o projeto, vá em Settings, Git,
  desconecte o repositório e conecte de novo. A publicação volta a sair a cada envio.

## As três frases do dia a dia

- **"sobe pro GitHub"**: o agente mesmo guarda o código no GitHub, e você só aprova. Em um ou dois
  minutos a Vercel publica sozinha.
- **"cria um usuário para o João, mestre"**: ou faça direto no Painel de admin do app, botão + Novo.
- **"o que mudou hoje?"**: numa conversa nova, na mesma pasta, o agente relê a pasta e te situa.
