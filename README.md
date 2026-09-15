# Arantes — Medicina da Pele

Landing page de uma clínica de dermatologia premium nos Jardins, em São Paulo, para mulheres de 35 a 60 anos. Site estático em HTML e CSS, com JavaScript mínimo e sem dependências nem etapa de build.

> **Aviso: projeto fictício de portfólio.** A clínica, as profissionais, os depoimentos e o endereço de número 716 foram inventados. Na versão publicada, CNPJ, CRM/RQE/COREN e telefones aparecem zerados, o Instagram foi removido e o botão de agendamento está desativado. Uma faixa no topo das duas páginas avisa que o site é fictício, e as páginas seguem com `noindex, nofollow`.

## Estrutura

```
site-clinica-estetica/
├── index.html              Landing page (HTML, CSS e JS no mesmo arquivo)
├── privacidade.html        Política de privacidade (LGPD)
├── favicon.svg             Monograma "A" (Newsreader) em Petróleo e Papel
├── favicon-32.png          Favicon para navegadores sem suporte a SVG
├── apple-touch-icon.png    Ícone 180×180 para iOS
├── icon-192.png            Ícones do manifest
├── icon-512.png
├── manifest.webmanifest
├── og-image.jpg            Pré-visualização em redes sociais (1200×630)
├── CNAME                   Domínio do GitHub Pages
├── README.md
└── docs/                   Planejamento (só local, fora do repositório)
```

O documento-mestre do projeto, com todas as decisões, é `docs/PROJETO.md`.

## Como rodar localmente

Não há instalação. Na pasta do projeto:

```bash
python -m http.server 8765
```

Abra `http://localhost:8765/`. Abrir o `index.html` direto do disco também funciona, mas algumas extensões do navegador bloqueiam `file://`.

As fontes (Google Fonts) e as fotos (Unsplash) são carregadas da internet.

## Publicação

- Publicado em **https://arantesdermato.zevro.app/** pelo GitHub Pages (branch `main`, raiz). O arquivo `CNAME` guarda o domínio.
- O domínio também aparece no `canonical`, nas tags Open Graph/Twitter, no `og:image` e no Schema JSON-LD de `index.html` e `privacidade.html`. Se mudar o endereço, substitua em todos esses pontos e no `CNAME`.
- A pasta `docs/` (planejamento) não vai para o repositório público: está no `.gitignore`.
- Para usar como clínica real: troque todos os dados fictícios, remova a faixa `.demo-note` e o aviso do rodapé, reative o botão de agendamento e só então troque `noindex, nofollow` por `index, follow`.
- Os e-mails exibidos (`contato@` e `privacidade@arantesdermato.zevro.app`) usam o domínio do site e não têm caixa criada.

## O que está implementado

- **SEO:** título e descrição únicos por página, `canonical`, Open Graph e Twitter Card, `lang="pt-BR"`, `theme-color`, um `h1` por página e hierarquia de títulos real.
- **Dados estruturados (JSON-LD):** `MedicalClinic` (endereço, horários, especialidade e tratamentos; sem telefone, CNPJ e registros na versão de demonstração), `Person` + `Physician` para a responsável técnica e as médicas da equipe (no Schema.org, `Physician` sozinho é um consultório, não uma pessoa), e `FAQPage` com as 7 perguntas da seção Dúvidas, com o mesmo texto da página.
- **Privacidade:** o site não usa cookies, analytics nem pixels, e por isso não precisa de aviso de cookies. A política explica o tratamento de dados de saúde, bases legais, prazos de guarda, direitos do titular e o contato do encarregado.
- **Acessibilidade:** link para pular ao conteúdo, foco visível, menu mobile que mantém o foco dentro dele enquanto está aberto (`inert` no conteúdo coberto), `alt` descritivo em todas as fotos, contraste AA e respeito a `prefers-reduced-motion`.
- **Movimento:** só CSS e um script pequeno com IntersectionObserver, sem bibliotecas. Detalhes em `docs/PROJETO.md` (Tarefa 5).

## Créditos

**Tipografia:** [Newsreader](https://fonts.google.com/specimen/Newsreader) (Production Type) e [Red Hat Text](https://fonts.google.com/specimen/Red+Hat+Text) (MCKL), ambas pela SIL Open Font License, via Google Fonts.

**Fotografias** do [Unsplash](https://unsplash.com), pela Unsplash License (uso comercial permitido, atribuição não obrigatória, creditada aqui por cortesia):

| Uso | Autor | Foto |
|---|---|---|
| Hero e og-image | Samuell Morgenstern | [unsplash.com/photos/H7D0UhmMbZc](https://unsplash.com/photos/H7D0UhmMbZc) |
| Retrato da Dra. Helena Arantes | Vitaly Gariev | [unsplash.com/photos/FC6CHluvgj8](https://unsplash.com/photos/FC6CHluvgj8) |
| Detalhe (tratamentos) | xandro Vandewalle | [unsplash.com/photos/CxmQXVqzyIE](https://unsplash.com/photos/CxmQXVqzyIE) |
| Clínica: corredor | kimia kazemi | [unsplash.com/photos/uzEWY67n-xE](https://unsplash.com/photos/uzEWY67n-xE) |
| Clínica: poltrona | Alina Bondar | [unsplash.com/photos/7mmmEkyk0aQ](https://unsplash.com/photos/7mmmEkyk0aQ) |
| Clínica: mesa junto à janela | Eric Human | [unsplash.com/photos/IIXtlWowNpQ](https://unsplash.com/photos/IIXtlWowNpQ) |

As pessoas das fotos são modelos de banco de imagens e não têm relação com a clínica fictícia.
