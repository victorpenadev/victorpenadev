# Fluxo Instagram: GitHub -> Metricool

## Estado validado em 2026-10-16

Conta de destino: Instagram conectado ao Metricool. O post de prova fica como `draft: true` e `autoPublish: false`. Nao foi publicado.

## Fluxo operacional

1. Produzir arte tipografica em SVG com `width="1080"` e `height="1350"` (formato 4:5).
2. Criar um arquivo com nome unico em `assets/instagram/YYYY-MM-DD-slug.svg` na branch `main`.
3. Montar a URL publica permanente:
   `https://raw.githubusercontent.com/victorpenadev/victorpenadev/main/assets/instagram/YYYY-MM-DD-slug.svg`
4. O Metricool rejeita SVG diretamente. Converter para PNG por URL HTTPS:
   `https://wsrv.nl/?url=raw.githubusercontent.com/victorpenadev/victorpenadev/main/assets/instagram/YYYY-MM-DD-slug.svg&output=png&w=1080`
5. Enviar a URL ao Metricool na propriedade `media`, com `providers: [{"network":"instagram"}]`, `instagramData: {"type":"POST"}`, `draft: true`, `autoPublish: false`.
6. Confirmar que a resposta da API contem `https://static.metricool.com/...png` em `media`, `draft: true`, `autoPublish: false`.
7. Conferir visualmente imagem e legenda no Metricool. Publicar ou agendar apenas com aprovacao expressa.

## Controle de qualidade

- Nunca criar um post com `autoPublish: true` sem autorizacao.
- Nunca prometer economia tributaria garantida ou sugerir sonegacao.
- Verificar ortografia, acentuacao, legibilidade no celular e enquadramento 4:5.
- Nao enviar dados de clientes, CPF, prontuarios, credenciais ou dados internos a URLs publicas.
- SVG publicos podem depender de fontes disponiveis no renderizador; conferir cada PNG importado.
- O conversor wsrv.nl e um servico de terceiros; o Metricool copia a imagem convertida para seu proprio CDN. Validar sempre a importacao e planejar armazenamento dedicado quando necessario.

## Primeiro teste de conteudo

- SVG: `2026-10-16-pagar-imposto-sem-conferir.svg`
- Mensagem: 'Pagar imposto sem conferir nao e gestao.'
- Rascunho no Metricool criado em 2026-10-16, sem publicacao automatica.
