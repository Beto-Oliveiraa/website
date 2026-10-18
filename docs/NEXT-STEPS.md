<!-- NEXT-STEPS.md — SEO and structure roadmap for the Beto Oliveira Personal Trainer site. Checklist of what to do, in priority order. -->

# Próximos passos (SEO)

Diagnóstico inicial: a base já é boa (`lang="pt-BR"`, `title` e `description` com local, um único `h1`, hierarquia `h2`/`h3`, viewport, HTML estático rápido). O que falta é principalmente **SEO local**, dados estruturados e conteúdo indexável.

## Ordem sugerida

1. Google Business Profile
2. JSON-LD, meta tags sociais, canonical, `robots.txt`, `sitemap.xml` e `noindex` no tapume
3. Imagens reais com `alt`
4. Páginas por região/serviço e blog
5. **Domínio próprio, só quando o site estiver próximo da versão final** (ver item 3)

---

## Alto impacto

### 1. Google Business Profile *(fora do código)*
Fator mais forte para buscas como "personal trainer Zona Sul" e "personal Niterói".
- [ ] Criar/reivindicar o perfil
- [ ] Usar o mesmo nome, telefone e site do site (consistência NAP)
- [ ] Definir categorias e áreas de atendimento
- [ ] Pedir avaliações a alunos

### 2. Dados estruturados (JSON-LD)
Hoje não existe nenhum. Adicionar um bloco `LocalBusiness` / `HealthAndBeautyBusiness` no `<head>` do [index.html](../index.html):

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HealthAndBeautyBusiness",
  "name": "Beto Oliveira Personal Trainer",
  "url": "<url final do site>",
  "telephone": "+5521998380814",
  "image": "<url absoluta do logo>",
  "areaServed": ["Zona Sul, Rio de Janeiro", "Niterói"],
  "sameAs": ["<instagram>", "<youtube>"]
}
</script>
```
- [ ] Implementar (usar URLs absolutas do domínio definitivo ao migrar)

### 3. Domínio próprio
O domínio final já existe, mas **só será associado quando o site estiver mais estruturado e próximo da versão final**. Até lá o site continua em `github.io/website/`.

- [ ] Antes da migração: deixar canonical, `og:url`, JSON-LD e `sitemap.xml` prontos para trocar a URL em um único passo
- [ ] Na migração: adicionar o domínio em *Settings → Pages → Custom domain* (o GitHub cria o arquivo `CNAME`) e configurar o DNS
- [ ] Depois: atualizar todas as URLs absolutas, enviar o sitemap no Search Console e manter o endereço antigo redirecionando

> Trocar de domínio depois de acumular links custa autoridade. Por isso, evite divulgar/linkar o endereço `github.io` em redes e diretórios enquanto a migração não acontecer.

### 4. Imagens reais com texto alternativo
As fotos de programas e blog são `<div class="photo" role="img">` com fundo em CSS, portanto **não são indexadas**.
- [ ] Trocar por `<img>` com `alt` descritivo, `width`/`height` e `loading="lazy"`
- [ ] Usar WebP/AVIF

## Médio impacto

### 5. Meta tags sociais e canonical
- [ ] `<link rel="canonical">`
- [ ] `og:title`, `og:description`, `og:image`, `og:type`, `og:url`
- [ ] `twitter:card`

Melhora a prévia ao compartilhar no WhatsApp e no Instagram.

### 6. `robots.txt` e `sitemap.xml`
- [ ] Criar os dois arquivos na raiz
- [ ] Cadastrar o site no Google Search Console

### 7. Esconder o `tapume.html`
Está publicado e indexável, com `title` quase igual ao da home.
- [ ] `<meta name="robots" content="noindex">` nele, ou removê-lo do deploy quando o site oficial estiver pronto

### 8. Títulos com palavra-chave
- [ ] Reforçar o `h1` com um subtítulo/texto de apoio citando "personal trainer na Zona Sul e em Niterói"
- [ ] Trocar `h3` genéricos ("AVALIAR", "PLANEJAR"…) ou complementá-los com termos como bioimpedância, avaliação física e treino online

## Conteúdo (sustenta o ranking a longo prazo)

### 9. Páginas por serviço e por região
Uma página única compete por todas as palavras-chave ao mesmo tempo.
- [ ] Ex.: `/personal-trainer-botafogo`, `/personal-trainer-niteroi`, `/treino-online`
- [ ] Evitar texto duplicado entre elas

### 10. Blog de verdade
Os 3 cards atuais são só vitrine.
- [ ] Cada card virar um artigo com URL própria
- [ ] Mirar cauda longa: "quanto custa personal trainer", "bioimpedância vale a pena"…

### 11. Sinais de confiança (E-E-A-T)
Saúde é categoria sensível para o Google.
- [ ] CREF visível na home (hoje está só no tapume)
- [ ] Formação e certificações
- [ ] Depoimentos com nome

## Técnico, baixo esforço

- [ ] `<link rel="preload">` para o logo (acima da dobra)
- [ ] Medir Core Web Vitals no PageSpeed Insights após trocar as imagens
- [ ] Corrigir os links de Instagram e YouTube (hoje apontam para `instagram.com/` e `youtube.com/` genéricos)
- [ ] Âncoras (`#sobre`) não geram URLs indexáveis; resolver com o item 9
