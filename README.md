# iGreen — Tianguá

Landing page independente, copiada integralmente de `cloudflare-worker/public/index.html` de `ronaelmoura/ronaelmoura.github.io`, commit `3ab1aa18ab66d5908debb331b961906e8b441959`.
A cópia `cloudflare-pages/index.html` da origem era idêntica. O repositório do portfólio não foi alterado.

## Estrutura

- `public/index.html`: página completa, com estilos e JavaScript incorporados.
- `wrangler.jsonc`: publica somente `public/` no Worker existente `igreen-tiangua`.

## Dados preservados

- Licenciado: Eli Jefferson — ID 114255.
- WhatsApp: 5586998081535.
- Conexão Green: https://green.igreenenergy.com.br/?id=114255
- Conexão Livre: https://livre.igreenenergy.com.br/?ref=d2f04f7e-500d-430e-9e1c-793936d64a06
- Licenciamento: https://expansao.igreenenergy.com.br/?id=114255&checkout=true&tipolicenca=CONNECT

O formulário abre uma mensagem no WhatsApp. Não há conexão ativa com CRM nesta versão.

## Conectar ao Worker existente

1. Na Cloudflare, abra Workers & Pages → igreen-tiangua → Settings → Builds (ou Build).
2. Desconecte o repositório antigo em Disconnect. Não exclua o Worker nem o repositório do portfólio.
3. Selecione Connect e conecte `ronaelmoura/igreen`. Se necessário, autorize este novo repositório na integração GitHub da Cloudflare.
4. Configure:

| Campo | Valor |
| --- | --- |
| Production branch | `main` |
| Root directory | `/` |
| Build command | `exit 0` |
| Deploy command | `npx --yes wrangler@4 deploy --config wrangler.jsonc` |

5. Salve e inicie um build do último commit de `main`. Confira o status de sucesso e a página publicada.

Endereço esperado: https://igreen-tiangua.ronaelmoura240.workers.dev

O repositório chama-se `igreen`; o nome do Worker permanece `igreen-tiangua` para preservar o endereço existente. A conexão e a publicação na Cloudflare são uma etapa posterior à criação deste repositório. Nenhuma alteração em anúncios ou contratação de serviços é necessária.

Documentação: https://developers.cloudflare.com/workers/ci-cd/builds/

## Verificação local sem publicar

```sh
npx --yes wrangler@4 deploy --dry-run --config wrangler.jsonc
```
