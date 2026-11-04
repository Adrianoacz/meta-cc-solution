# meta-cc-solution

Skill para o Claude que consulta a documentação oficial e atual da Meta antes de responder. Serve
para resolver problemas e seguir passo a passo em:

- Graph API, Marketing API e API de Conversões (Pixel);
- WhatsApp Cloud API: números, modelos de mensagem, webhooks e erros;
- Meta Business Suite e Gerenciador de Negócios;
- verificação do negócio, revisão do app, permissões e tokens;
- políticas de anúncio.

A Meta muda versões, permissões e regras com frequência. Em vez de responder de memória, a skill lê
a página oficial na hora, cita o link de cada passo e diz claramente o que não conseguiu confirmar.

Feita pela [CCSolutions](https://ccsolutions.pages.dev), em português, para o público brasileiro.

## Instalação

Requer o Claude Code com acesso à web (WebFetch e WebSearch).

**Com git:**

```
git clone <endereço-deste-repositório> ~/.claude/skills/meta-cc-solution
```

**Sem git:** baixe o zip deste repositório, extraia e coloque a pasta em
`~/.claude/skills/meta-cc-solution/`. No Windows, `~` é a sua pasta de usuário, por exemplo
`C:\Users\seu-nome\.claude\skills\meta-cc-solution\`.

O arquivo `SKILL.md` precisa ficar direto dentro da pasta `meta-cc-solution`. Abra uma conversa nova
no Claude Code para a skill aparecer.

## Como usar

Fale normalmente. A skill entra quando o assunto é Meta, Facebook, Instagram ou WhatsApp. Exemplos:

- "meu template do whatsapp foi rejeitado como marketing, mas é aviso de pedido"
- "a API devolve erro 190 com subcode 463, o que faço?"
- "quero ligar a API oficial do WhatsApp no meu número, me dá o passo a passo"
- "a revisão do app recusou a permissão pages_manage_posts"
- "como verifico minha empresa no Business Suite?"

A resposta vem com diagnóstico (quando é problema), passo a passo com links, as páginas conferidas e
o que ficou sem confirmação.

## O que ela lê e o que não lê

Testado em 04/11/2026:

- **Lê direto:** a documentação de desenvolvedor (`developers.facebook.com`) e os Padrões de
  Publicidade (`transparency.meta.com`). Páginas muito longas chegam cortadas; a skill abre a
  subpágina do assunto. A documentação do WhatsApp está mudando de endereço, e a skill já aponta para
  o caminho novo.
- **Não lê direto:** a Central de Ajuda para Empresas e a do WhatsApp, que só devolvem o título. A
  skill lê pelo r.jina.ai (veja abaixo), busca a página equivalente para desenvolvedores ou pede que
  você cole o texto.
- **Não lê:** o metastatus.com. Quando o problema parecer geral, a skill pede que você abra a página.

## Sobre o r.jina.ai

Para ler páginas públicas da Central de Ajuda, a skill pode usar o [r.jina.ai](https://jina.ai/reader),
um serviço gratuito de terceiros que converte páginas em texto. Ele recebe apenas o endereço da página
pública de ajuda, nunca token, ID de conta ou dado seu. O serviço pode mudar ou limitar o uso sem
aviso. Se preferir não usar, apague a seção do contorno 2 em `references/fontes.md`.

## Segurança

A skill não pede token, chave secreta do app nem senha. Se você colar um token no chat, ela vai
recomendar que você gere outro. Antes de orientar algo que apaga ou altera a sua conta, ela explica o
que se perde e pede confirmação.

## Aviso

Projeto independente, sem vínculo com a Meta Platforms, Inc. Meta, Facebook, Instagram e WhatsApp são
marcas da Meta. A skill orienta com base na documentação pública; a decisão e a execução na sua conta
são suas.

## Licença

[MIT](LICENSE).
