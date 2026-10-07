# Relatório final: Dárquia Moreira, Psicóloga Clínica

Modo PRIMEIRO-SITE. Fases: direção visual (taste-skill), construção (impeccable) e polimento de movimento (emil-design-eng).

## 1. Informações que faltaram e como foram contornadas

| Item | Situação | Como foi contornado |
|---|---|---|
| Logotipo | Não existe arquivo de logo. O nome em cursiva no site atual é fonte de texto. | Nome composto em texto (Outfit). Favicon provisório feito de um recorte da foto dela. |
| Valores das sessões | Não podem ser divulgados (orientação do CFP, dita no site atual). Doctoralia mostra R$150 e R$200, divergentes. | Nada publicado. FAQ explica e leva ao WhatsApp. |
| Horários de atendimento | Sem fonte confiável (só um resumo gerado pelo Google, cortado). | Omitidos. "Combine o horário pelo WhatsApp". |
| Detalhes dos planos | Nenhuma fonte descreve sessão pontual, plano de 90 e de 180 dias. | Textos genéricos, sem preço e sem promessa, autorizados pelo responsável. Frequência "combinada com a psicóloga". |
| Estatísticas (sessões, anos de experiência) | Não existem nas fontes. | Não usadas. |
| CEP da Mooca | Não encontrado de forma confiável. | Endereço sem CEP. |
| Link do perfil no Google Maps | Só havia a busca do Google. | Os botões "Ver todas as avaliações" e o ícone do Google abrem a busca. Trocar pelo link de compartilhamento do Maps. |
| Instagram | Feed e links extras atrás de login. | Usados só nome, CRP e bio visíveis, mais o trecho "online e presencial" achado na busca. |
| Mapa incorporado | Evitado por performance. | Botões "Abrir no mapa" (Google Maps) para cada endereço. |

Avaliações do Google (perfil de Mauá, 5,0 com 57 avaliações), lidas em 07/10/2026. Exibidas 5, copiadas ao pé da letra: Thaissa Sobrinho, Carolina Nascimento, Nicole Gussonato (primeira frase), Júlia De Araújo (primeira frase) e Rafael Magalhaes. Ficaram de fora Nayara Oliveira (erro de digitação no original), Evilyn Meireles (texto curto demais) e Alexandre Abreu (frase final informal). O perfil de São Paulo (63 avaliações, 5,0) não foi lido.

## 2. GoatCounter

- **Script no `<head>`, endereço exato:** `<script data-goatcounter="https://teocode.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>`
- **Eventos de CTA (12):** `cta-nav`, `cta-menu`, `cta-hero`, `cta-servicos`, `cta-avaliacoes`, `cta-plano-pontual`, `cta-plano-90-dias`, `cta-plano-180-dias`, `cta-faq`, `cta-contato`, `cta-footer`, `cta-flutuante`.
- **Listener único** em JS puro, com `if (window.goatcounter && window.goatcounter.count)`. O link do WhatsApp funciona mesmo com adblock.
- **Onde ver:** Dashboard > Events. O domínio publicado precisa estar cadastrado no painel do GoatCounter.

## 3. Pendências que dependem do cliente

1. Confirmar o que cada plano inclui (frequência, duração, o que está incluso).
2. Aprovar a primeira pessoa da seção "Conheça a Dárquia" (voz dela, redigida a partir de site, Instagram e Doctoralia).
3. Enviar o logo, se existir, para trocar o nome em texto e o favicon.
4. Enviar o link de compartilhamento do perfil no Google Maps (Mauá).
5. Confirmar o domínio final (`canonical`, `og:url`, `og:image` e JSON-LD hoje apontam para `gustavoteodoro10.github.io/PsicoDarquiaMoreira/`).
6. Confirmar se quer mostrar horários e, se sim, quais.
7. Cadastrar o domínio no GoatCounter (`teocode`).

## O que foi aproveitado de cada referência

- **Referência 1 (Viviane), "O que dizem os pacientes":** linha-resumo com a nota do Google e link de validação; citações com inicial como avatar, nome e atribuição; link "Ver todas as avaliações". Descartado: estatísticas de sessões e anos, seção de brasileiros no exterior, mentoria e a pill de status no hero.
- **Referência 2 (Luana), "o conjunto":** navegação de uma linha com um único CTA de WhatsApp; hero dividido com foto e nome + CRP; três formas de atendimento (pontual, 90 e 180 dias); botão flutuante; um CTA por seção e fluxo curto. Descartado: paleta terracota, conteúdo de neuropsicologia, foto da sala e selos de diretórios.

Nenhum texto, imagem, código, cor ou identidade das referências foi copiado.

## Resultado do polimento (emil-design-eng)

| Antes | Depois | Por quê |
|---|---|---|
| Hover com elevação de 2 px em todo botão | Só troca de cor e seta de 3 px, e apenas com mouse | Hover repetido dezenas de vezes por dia deve ser discreto; celular não dispara hover |
| Press `scale(.98)` em 250 ms | `scale(.97)` em 160 ms em botões, links, menu, redes e FAQ | Resposta imediata ao toque |
| Revelação de 800 ms com 18 px de deslocamento | 600 ms com 14 px; cartões com escala .98; citações só com fade | Mais rápido, e entradas diferentes por tipo de bloco |
| Easing `cubic-bezier(.16,1,.3,1)` | `cubic-bezier(.23,1,.32,1)` como `--ease` | Ease-out forte e consistente |
| FAQ abria em corte seco | Abre e fecha com animação de altura e fade (`::details-content`) | Evita mudança brusca; cai para abertura simples sem suporte |
| Menu móvel aparecia de uma vez | Entra em 180 ms (`@starting-style`); sai na hora | Assimetria: lento onde há entrada, rápido onde o sistema responde |
| Hero entrava todo junto | Texto em sequência, foto assenta, cartão do nome por último; botão do WhatsApp surge depois de 1,2 s | Hierarquia e narrativa de leitura |
| Estrelas estáticas | Estrelas da avaliação em destaque acendem em sequência (60 ms) | Momento raro e de primeira visita, onde um pouco de encanto cabe |
| Movimento reduzido zerava todas as transições | Fades curtos de 300 ms e trocas de cor mantidos; sem deslocamento | Reduzido não significa zero |

## Registro do processo

- A revisão final e o DESIGN.md foram feitos na própria conversa, porque os agentes dedicados do impeccable não existem neste ambiente.
- O detector de design foi rodado uma vez e deixou 2 avisos mecânicos não investigados (espaçamento do menu móvel e uma entrelinha de 1,18 em algum texto).
- Não foi rodado Lighthouse; o desempenho foi cuidado por construção (imagens WebP com dimensões, lazy loading, sprite SVG inline, JS mínimo, fontes com `display=swap`). O Tailwind via CDN, exigido pelo padrão, é a maior fatia de peso.
- O painel de pré-visualização do app atrasa animações e o disparo do `IntersectionObserver`. As animações foram checadas com espera e chegam ao estado final; vale conferir a sensação de tempo no navegador real e em um celular.
