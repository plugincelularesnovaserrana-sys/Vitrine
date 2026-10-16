# Vitrine · Plugin Celulares

Catálogo virtual publicado no GitHub Pages. Todas as páginas leem a mesma lista (`produtos.json`), que é atualizada pelo `admin.html`.

## Páginas

| Página | Link | O que mostra |
|---|---|---|
| `boleto.html` | `.../Vitrine/boleto.html` | Só **entrada mínima + parcelas** do boleto, com filtro "Parcela até R$ X". Use no anúncio do boleto. |
| `cartao.html` | `.../Vitrine/cartao.html` | **À vista com desconto** (PIX/dinheiro) + **cartão sem juros**. |
| `index.html` | `.../Vitrine/` | Catálogo completo (à vista, cartão e boleto). |
| `admin.html` | `.../Vitrine/admin.html` | Cadastro dos aparelhos e envio da lista para o GitHub. |

No catálogo do boleto só aparecem aparelhos que têm boleto preenchido no admin.

## Arquivos

- `catalogo.js` – configuração (WhatsApp, selos, listaUrl), textos de cada vitrine e todo o funcionamento.
- `catalogo.css` – visual das três vitrines.
- `produtos.json` – lista de aparelhos (gerada pelo admin).
- `assets/` – fotos e logo.

## Preços no admin

- **À vista** – preço com desconto (PIX ou dinheiro).
- **Cartão** – preço no cartão + parcelas sem juros (padrão 10x). O valor da parcela é calculado sozinho.
- **Boleto** – entrada mínima + parcelas + valor da parcela (padrão 15x para iPhone, 11x para Android).

Formato gravado no JSON:

```json
"preco": 2700,
"cartao": {"total": 2970, "parcelas": 10, "parcela": 297},
"boleto": {"entrada": 799.9, "parcelas": 15, "parcela": 299.9}
```

## Ao alterar catalogo.js ou catalogo.css

As páginas carregam `catalogo.js?v=4` e `catalogo.css?v=4`. Ao publicar mudanças nesses arquivos, troque o número (`v=5`, `v=6`...) nas três páginas HTML para os celulares dos clientes pegarem a versão nova.
