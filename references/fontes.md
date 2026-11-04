# Fontes oficiais da Meta

Pontos de partida por área. A coluna "Leitura" mostra o resultado dos testes de 04/11/2026 com
WebFetch. Endereços mudam: se um deles der 404, busque o título do assunto com WebSearch em
`developers.facebook.com`.

## Sumário

1. Graph API, versões e erros
2. App, permissões e revisão do app
3. Verificação do negócio
4. WhatsApp
5. Anúncios, Marketing API e API de Conversões
6. Central de Ajuda e status
7. Quando a página não abre

## 1. Graph API, versões e erros

| Assunto | Endereço | Leitura |
|---|---|---|
| Changelog e versão atual | https://developers.facebook.com/docs/graph-api/changelog | Completa, em português |
| Mudanças de uma versão | https://developers.facebook.com/docs/graph-api/changelog/version26.0 (trocar o número) | Completa |
| Tratamento de erros e códigos | https://developers.facebook.com/docs/graph-api/guides/error-handling | Completa, em português |

A página geral do changelog pode citar uma versão cuja página ainda não existe (nos testes, citava a
v27.0, e a página dela dava 404). Para afirmar a versão atual ou um prazo de descontinuação, use a
página da versão que abre.

## 2. App, permissões e revisão do app

| Assunto | Endereço | Leitura |
|---|---|---|
| Criar um app | https://developers.facebook.com/docs/development/create-an-app | Completa |
| Revisão do app | https://developers.facebook.com/docs/app-review | Resumo e links; seguir os links |
| Referência de permissões | https://developers.facebook.com/docs/permissions | Cortada na metade por ser longa |

Para uma permissão específica, busque o nome dela (por exemplo `whatsapp_business_messaging`) em vez
de depender da página inteira.

## 3. Verificação do negócio

| Assunto | Endereço | Leitura |
|---|---|---|
| Verificação, visão do desenvolvedor | https://developers.facebook.com/docs/development/release/business-verification | Completa |
| Como verificar no Business Suite (passo a passo de tela, prazo, métodos de confirmação) | https://www.facebook.com/business/help/2058515294227817 | Só pelo r.jina.ai (seção 7); veio completo |

A página de desenvolvedor só cobre ligar o app a um negócio já verificado. O passo a passo da
verificação está na Central de Ajuda. O que a verificação libera no WhatsApp está na seção 4.

## 4. WhatsApp

A documentação está migrando para `developers.facebook.com/documentation/business-messaging/whatsapp/`.
Os endereços antigos (`/docs/whatsapp/...`) ainda abrem, mas costumam ser visões gerais; o detalhe
fica no caminho novo.

| Assunto | Endereço | Leitura |
|---|---|---|
| Índice da documentação nova | https://developers.facebook.com/documentation/business-messaging/whatsapp/llms.txt | Completa; comece por aqui para achar a página |
| Visão geral da plataforma (o que a verificação libera) | https://developers.facebook.com/documentation/business-messaging/whatsapp/about-the-platform | Completa |
| Limites de mensagens | https://developers.facebook.com/documentation/business-messaging/whatsapp/messaging-limits | Completa |
| Categorias de modelo | https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/template-categorization | Completa |
| Análise e rejeição de modelo | https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/template-review | Completa |
| Edição e gestão de modelo | https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/template-management.md | Completa |
| Modelos, visão geral | https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates | Visão geral; detalhe nas páginas acima |
| Primeiros passos na Cloud API | https://developers.facebook.com/docs/whatsapp/cloud-api/get-started | Completa, em inglês |
| Códigos de erro | https://developers.facebook.com/docs/whatsapp/cloud-api/support/error-codes | Completa |
| Contas e números | https://developers.facebook.com/docs/whatsapp/overview/business-accounts | Completa |
| Preços | https://developers.facebook.com/docs/whatsapp/pricing | Cortada perto de 2/3 |
| Central de Ajuda do WhatsApp | https://faq.whatsapp.com/ | Só a casca; usar contornos |

Se uma página antiga e uma nova disserem coisas diferentes (nos testes, limites de mensagens por
número contra limites por portfólio), vale a nova, e a diferença deve ser citada na resposta.

O parâmetro `?locale=pt_BR` não traduz a documentação do WhatsApp. Leia em inglês e responda em
português.

## 5. Anúncios, Marketing API e API de Conversões

| Assunto | Endereço | Leitura |
|---|---|---|
| Marketing API, primeiros passos | https://developers.facebook.com/docs/marketing-api/get-started | Resumo e links |
| API de Conversões | https://developers.facebook.com/docs/marketing-api/conversions-api | Resumo e links |
| Padrões de publicidade (políticas) | https://transparency.meta.com/policies/ad-standards | Cortada perto de 4/5 |

## 6. Central de Ajuda e status

| Assunto | Endereço | Leitura |
|---|---|---|
| Central de Ajuda para Empresas | https://www.facebook.com/business/help | Só o título; usar contornos |
| Status dos produtos | https://metastatus.com | Não abre; pedir ao usuário |

A Central de Ajuda é onde ficam as orientações de tela do Business Suite e do Gerenciador de
Negócios. Ela é montada por JavaScript, e a leitura direta devolve só o título.

## 7. Quando a página não abre

Para a Central de Ajuda (`facebook.com/business/help` e `faq.whatsapp.com`), não tente a leitura
direta: ela devolve só o título. Comece pelo passo 1. Para outras páginas, siga a ordem e pare no
primeiro que funcionar:

1. **Leitor r.jina.ai, só para página pública.** Leia `https://r.jina.ai/` seguido do endereço
   completo, por exemplo `https://r.jina.ai/https://www.facebook.com/business/help/2058515294227817`.
   Nos testes, devolveu o artigo inteiro da Central de Ajuda, em inglês. É um serviço de terceiros,
   gratuito, que pode mudar ou limitar o uso. Nunca use com endereço que tenha token, ID ou dado do
   usuário. Para status, ele devolve uma cópia antiga: não use para isso.
2. **Equivalente na documentação de desenvolvedor.** Alguns assuntos da Central de Ajuda têm uma
   página em `developers.facebook.com`. Busque com WebSearch o assunto restrito a esse domínio. Ela
   costuma complementar, não substituir: o passo a passo de tela fica na Central de Ajuda.
3. **Busca.** Use WebSearch com o título do artigo. Prefira resultados de domínios da Meta. Guia de
   terceiro serve como pista e deve ser identificado como não oficial na resposta.
4. **Usuário.** Peça para ele abrir a página e colar o texto ou enviar um print. Diga exatamente qual
   página abrir.

Página longa cortada: abra a subpágina do assunto ou busque o termo exato, em vez de reler a página
inteira.
