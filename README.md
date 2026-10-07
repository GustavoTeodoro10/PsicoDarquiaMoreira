# Dárquia Moreira, Psicóloga Clínica

One-page em HTML/CSS/JS puro com Tailwind CSS via CDN. Sem build, backend ou CMS. Todos os botões levam ao WhatsApp **(11) 98593-9585** com mensagem pré-programada por seção.

## Estrutura

```
PsicoDarquiaMoreira/
├─ index.html              # a página inteira (HTML + CSS dos tokens + JS mínimo)
├─ assets/
│  ├─ img/
│  │  ├─ darquia-hero.webp / darquia-hero-640.webp     # retrato do hero
│  │  ├─ darquia-sobre.webp / darquia-sobre-600.webp   # retrato da seção Sobre
│  │  ├─ og-darquia.jpg                                # preview do WhatsApp/Instagram (1200x630)
│  │  └─ favicon-32.png, favicon-256.png, apple-touch-icon.png   # recorte da foto dela
│  └─ icons/sprite.svg     # ícones Phosphor (já embutidos no index.html)
├─ PRODUCT.md              # fatos confirmados do cliente (contexto do projeto)
└─ README.md
```

## Como rodar localmente

Abra o `index.html` no navegador, ou sirva a pasta:

```bash
python -m http.server 5173
```

e acesse http://localhost:5173.

## O que editar (procure por `EDITÁVEL` no index.html)

| Item | Onde |
|---|---|
| Textos do hero, temas, planos e FAQ | seções comentadas com `EDITÁVEL` |
| Número e mensagens do WhatsApp | links `https://wa.me/5511985939585?text=...` (a mensagem vai codificada na URL) |
| Fotos | `assets/img/` (mantenha as proporções 4:5) |
| Avaliações | seção `#avaliacoes` (copie o texto original do Google) |
| URL final do site | `canonical`, `og:url`, `og:image` e o JSON-LD no `<head>` |
| Cores e fontes | bloco `:root` no `<style>` (tokens claro e escuro) |

## Movimento e microinterações

Tudo em CSS, sem biblioteca. As regras ficam no bloco `Movimento` do `<style>` do `index.html`.

- **Curvas:** `--ease` (ease-out forte) para toda interação de UI e `--ease-in-out` para movimento na tela. Nada usa `ease-in` nem `transition: all`.
- **Duração:** pressionar e trocar de cor 150 a 200 ms; revelações 600 ms; entrada do hero 700 a 900 ms.
- **Pressão:** botões, links, menu, redes sociais e FAQ encolhem para 0,97 ao toque (`:active`).
- **Hover:** só em dispositivos com mouse (`@media (hover: hover) and (pointer: fine)`), para o celular não disparar hover ao tocar. Botões trocam de cor, setas deslocam 2 a 3 px e os cartões sobem 2 px.
- **Hero:** o texto sobe em sequência (70 ms de intervalo), a foto assenta e o cartão com o nome aparece por último.
- **Rolagem:** `IntersectionObserver` (sem listener de scroll). Títulos sobem, cartões assentam com escala 0,98 e as citações só aparecem. As 5 estrelas da avaliação em destaque acendem em sequência.
- **FAQ:** abre e fecha com animação de altura (`::details-content`, Chrome 131+). Em navegadores sem suporte, abre sem animação.
- **Menu móvel:** entra em 180 ms; fecha na hora (ação do usuário pede resposta imediata).
- **Movimento reduzido (`prefers-reduced-motion`):** some o deslocamento e ficam só fades curtos (300 ms) e trocas de cor. Sem JavaScript, todo o conteúdo fica visível.

## Deploy gratuito

**GitHub Pages:** suba a pasta em um repositório, vá em *Settings > Pages*, escolha a branch `main` e a pasta `/ (root)`. O endereço padrão fica `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

**Netlify ou Cloudflare Pages:** arraste a pasta no painel (Netlify Drop) ou conecte o repositório. Não há comando de build; o diretório de publicação é a raiz.

**Domínio próprio:** registre o domínio, aponte o DNS para o provedor escolhido (CNAME para GitHub Pages, ou o domínio nas configurações do Netlify/Cloudflare) e depois atualize `canonical`, `og:url`, `og:image` e o JSON-LD no `<head>` com o endereço final.

## GoatCounter (analytics sem cookies)

- **Onde está o script:** no `<head>` do `index.html`:

  ```html
  <script data-goatcounter="https://teocode.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>
  ```

- **Eventos de clique (um por CTA):** `cta-nav`, `cta-menu`, `cta-hero`, `cta-servicos`, `cta-avaliacoes`, `cta-plano-pontual`, `cta-plano-90-dias`, `cta-plano-180-dias`, `cta-faq`, `cta-contato`, `cta-footer`, `cta-flutuante`.
- **Como funciona:** um único listener no final do `index.html` lê o atributo `data-gc-event` do botão clicado e chama `window.goatcounter.count({ path, title, event: true })`. O link do WhatsApp abre normalmente mesmo se o rastreio estiver bloqueado (adblock).
- **Onde ver:** no painel do GoatCounter, em *Dashboard > Events*.
- **Lembrete:** o domínio onde o site for publicado precisa estar cadastrado no painel do GoatCounter (`teocode`) para os acessos serem contabilizados.

## Créditos

Site desenvolvido por [TeoCode](https://teocode.com.br/). Ícones: Phosphor Icons (MIT). Fontes: Outfit e Figtree (Google Fonts, OFL).
