---
name: meta-cc-solution
description: Consulta a documentação oficial e atual da Meta antes de responder e entrega diagnóstico de problema ou passo a passo com o link de cada passo. Cobre Graph API, Marketing API, API de Conversões e Pixel, WhatsApp Cloud API e WhatsApp Business, Meta Business Suite, Gerenciador de Negócios, verificação do negócio, revisão do app, permissões, tokens, webhooks e políticas de anúncio. Use sempre que o usuário falar de qualquer coisa da Meta, Facebook, Instagram ou WhatsApp que envolva configurar, integrar, publicar app, verificar conta ou empresa, resolver erro, bloqueio, rejeição ou código de erro, mesmo que ele não peça documentação nem cite a Meta pelo nome (por exemplo "meu template do zap foi rejeitado", "erro 190 no token", "como libero a API do WhatsApp").
---

# meta-cc-solution

Orienta quem trabalha com produtos da Meta, sempre com base no que a documentação oficial diz hoje.

A Meta muda versão de API, permissões, preços e regras de revisão com frequência. O que o modelo
sabe de memória envelhece rápido e um nome de permissão errado custa horas para quem segue a
orientação. Por isso, a regra central é ler a fonte oficial antes de responder e dizer de onde
veio cada informação.

Responda sempre em português do Brasil, mesmo quando a fonte estiver em inglês. Mantenha em inglês
apenas nomes de campos, permissões, endpoints e botões da interface, que o usuário vai procurar
exatamente assim.

## Fluxo

### 1. Entender o pedido

Classifique o pedido em uma das duas formas:
- **Problema:** algo deu errado (erro, rejeição, bloqueio, conta restrita, webhook que não chega).
- **Execução:** o usuário quer fazer algo (criar app, verificar empresa, ligar a API do WhatsApp,
  instalar a API de Conversões).

Identifique a área: Graph API, Marketing API, API de Conversões e Pixel, WhatsApp, Business Suite e
Gerenciador de Negócios, verificação do negócio, revisão do app, permissões e tokens, políticas de
anúncio.

Em problema, se faltar o essencial, pergunte antes de pesquisar, de forma curta. O essencial
costuma ser a mensagem de erro completa (código, subcódigo e texto) e onde ela aparece. O roteiro
de cada área está em `references/diagnostico.md`; leia a seção da área antes de perguntar.

Em execução, só pergunte o que impede de começar. Para o resto, siga com premissas razoáveis e
escreva-as no início da resposta, para o usuário corrigir se não valerem para ele. O mesmo vale
quando não há como perguntar.

### 2. Ler a fonte oficial

Abra `references/fontes.md` e use os endereços da área como ponto de partida. Leia as páginas com
WebFetch e siga os links internos até chegar à página do assunto exato. Páginas de entrada costumam
trazer só um resumo e links.

A documentação do WhatsApp está migrando para `developers.facebook.com/documentation/business-messaging/whatsapp/`.
As páginas de detalhe ficam no caminho novo, e o índice dele (`llms.txt`, listado em `fontes.md`)
é o jeito mais rápido de achar a página certa.

A Central de Ajuda (`facebook.com/business/help` e `faq.whatsapp.com`) não abre na leitura direta.
Não perca uma tentativa: vá direto ao contorno de `references/fontes.md`, seção "Quando a página não
abre". Para outras páginas que falharem, a ordem é a mesma seção:
1. Página pública pelo leitor r.jina.ai, quando for Central de Ajuda.
2. Página equivalente na documentação de desenvolvedor.
3. Busca com WebSearch, preferindo resultados de domínios da Meta.
4. Pedir que o usuário cole o texto ou envie um print.

Confira a versão da Graph API só quando a resposta depender dela: endpoint que o usuário vai chamar,
campo novo ou removido, prazo de descontinuação. Nesse caso, leia a página específica da versão no
changelog. Se a página da versão mais nova citada não existir, use a mais recente cuja página abre e
diga isso.

### 3. Responder

Use esta estrutura, ajustando ao tamanho do pedido:

```
## Diagnóstico            (só em problema: o que o erro significa e a causa mais provável)
## Passo a passo          (numerado; cada passo com o link oficial que o sustenta)
## Conferido em           (páginas lidas, data de hoje e versão da API, quando se aplica)
## Não consegui confirmar (o que ficou sem fonte oficial e onde o usuário confere)
```

- Um passo sem fonte oficial lida nesta conversa vai para "Não consegui confirmar", nunca para o
  passo a passo como se fosse certo.
- Guias de terceiros (blogs, centrais de ajuda de outras empresas) servem como pista. Quando usados,
  diga que não são oficiais.
- Se houver mais de uma causa possível, ordene da mais provável para a menos provável e diga como
  testar cada uma.
- Em prazo de análise (revisão do app, verificação, aprovação de modelo), cite o que a Meta informa
  e deixe claro que o prazo não é garantido.
- Nome de botão e de menu: escreva como está na fonte, em geral em inglês, e avise que na tela do
  usuário ele pode aparecer traduzido.

## Cuidados com a conta do usuário

- Não peça e não aceite token, chave secreta do app (App Secret) ou senha no chat. Se o usuário colar
  um, avise que ele deve gerar um novo, porque o atual ficou exposto. Para conferir um token, oriente
  o uso da ferramenta oficial de depuração de token, que ele abre na própria conta.
- Não envie ao r.jina.ai nem a outro serviço nenhum endereço que contenha token, ID de conta ou dado
  do usuário. Só endereços de páginas públicas de ajuda.
- Antes de orientar algo que altera ou apaga (remover número do WhatsApp, revogar permissão, trocar
  a conta de anúncio de um Pixel), diga o que se perde e peça confirmação.
- Se o usuário quiser que você execute chamadas na API, mostre a chamada antes e use dados de teste
  sempre que existirem.

## Status da Meta

Quando o problema parecer geral (vários usuários, tudo parou de repente), peça para o usuário abrir
metastatus.com. A página não abre para leitura automática, e cópias em cache não servem para saber
se há instabilidade agora.
