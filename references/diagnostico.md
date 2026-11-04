# Roteiros de diagnóstico

O que perguntar e o que conferir em cada tipo de problema. Os roteiros dizem onde olhar; o
significado de cada código, os limites e os prazos vêm sempre da documentação lida na hora.

## Sumário

1. Qualquer erro de API
2. Token e permissões
3. Revisão do app
4. Verificação do negócio
5. WhatsApp: envio de mensagem
6. WhatsApp: modelos (templates)
7. WhatsApp: webhook
8. Pixel e API de Conversões
9. Anúncio rejeitado ou conta restrita

## 1. Qualquer erro de API

Peça ao usuário:
- a resposta de erro completa: `code`, `error_subcode`, `message`, `type` e `fbtrace_id`;
- o endpoint chamado e a versão da API no endereço (por exemplo `v26.0`);
- se funcionava antes e o que mudou.

Confira na página de tratamento de erros da Graph API e, para WhatsApp, na de códigos de erro da
Cloud API. O `fbtrace_id` é o que o suporte da Meta pede, caso o usuário precise abrir chamado.

## 2. Token e permissões

Pergunte:
- o tipo de token: de usuário, de página, de usuário do sistema ou de app;
- quando ele foi gerado e se o usuário trocou a senha ou removeu o app depois disso;
- quais permissões o token tem (ver na ferramenta oficial de depuração de token).

Confira:
- se o token venceu ou foi invalidado;
- se a permissão necessária para o endpoint foi concedida e, quando exigido, aprovada na revisão do
  app;
- se o app está em modo de desenvolvimento, que limita o acesso a quem tem função no app.

Lembre o usuário de não colar o token no chat.

## 3. Revisão do app

Pergunte quais permissões ou recursos foram pedidos e qual foi o motivo da rejeição, com o texto da
Meta.

Confira na documentação da revisão do app:
- se cada permissão pedida é usada de fato pelo app e se o uso aparece no vídeo de demonstração;
- se as instruções de teste permitem ao revisor reproduzir o uso;
- se a verificação do negócio é exigida para o que foi pedido;
- se a política de privacidade está no ar e acessível.

## 4. Verificação do negócio

Pergunte o que aparece na Central de Segurança das configurações do negócio e o texto da rejeição,
se houver.

Confira:
- se o nome jurídico informado é idêntico ao do documento enviado (no Brasil, o do CNPJ);
- se endereço, telefone e site batem com o documento e entre si;
- se o documento está legível e dentro da lista aceita;
- se o e-mail ou o domínio usado na confirmação pertence à empresa.

A orientação de tela fica na Central de Ajuda; use os contornos de `fontes.md` para lê-la.

## 5. WhatsApp: envio de mensagem

Pergunte o código de erro, o tipo de mensagem (texto livre ou modelo) e se é o primeiro contato com
aquele cliente.

Confira na documentação:
- a janela de atendimento: fora dela, só modelo aprovado pode ser enviado;
- o status do número: conectado, nome de exibição aprovado, classificação de qualidade e limite de
  mensagens;
- a forma de pagamento da conta do WhatsApp Business;
- o formato do número de destino (código do país, sem símbolos).

## 6. WhatsApp: modelos (templates)

Pergunte a categoria escolhida, o texto do modelo e o motivo da rejeição.

Confira na página de modelos:
- se a categoria corresponde ao conteúdo (marketing, utilidade, autenticação);
- variáveis: formato e exemplos preenchidos;
- limites de criação e regras de conteúdo.

## 7. WhatsApp: webhook

Pergunte se a verificação do endereço passou, se o app está inscrito nos campos certos e se algum
evento chega.

Confira:
- se o endereço é público, com HTTPS válido, e responde à verificação com o desafio enviado pela
  Meta;
- se o app está inscrito no campo de mensagens da conta do WhatsApp Business;
- se o servidor responde rápido com sucesso, para a Meta não reenviar nem desativar.

## 8. Pixel e API de Conversões

Pergunte se o evento aparece no Gerenciador de Eventos, se a origem é navegador, servidor ou as duas,
e o que o diagnóstico do Gerenciador de Eventos mostra.

Confira:
- a desduplicação entre navegador e servidor, pelo identificador de evento;
- a qualidade dos dados do cliente enviados (correspondência);
- o token de acesso da API de Conversões e o ID do Pixel.

## 9. Anúncio rejeitado ou conta restrita

Pergunte o texto da rejeição ou da restrição e a política citada.

Confira nos Padrões de Publicidade a política citada e o que ela exige. Explique como pedir nova
análise pelo caminho oficial e deixe claro que o resultado não é garantido.
