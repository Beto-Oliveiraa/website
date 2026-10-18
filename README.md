<!-- README.md — How to run, edit and publish the Beto Oliveira static site. -->
# Beto Oliveira Personal Trainer — site estático

HTML + CSS puro, sem build e sem JS.

## Rodar localmente
```bash
python3 -m http.server 8000   # abrir http://localhost:8000
```

## Fotos
Coloque os arquivos em `assets/img/` com estes nomes (enquanto não existirem, aparece um gradiente):

| Arquivo     | Onde aparece                       |
|-------------|------------------------------------|
| `hero.jpg`  | Fundo do hero (foto do Beto à direita) |
| `about.jpg` | Seção "Sobre mim"                  |
| `gym.jpg`   | Faixa lateral de "Serviços"        |

Os cards (público, programas, blog) usam a variável `--img` — exemplo:
`<div class="photo" style="--img:url(assets/img/mulheres.jpg)">`.

## Pendências
- Trocar o número do WhatsApp (`5521999999999`) e links de Instagram/YouTube.
- Datas e textos do blog são exemplos.

## GitHub Pages
Repositório → Settings → Pages → Deploy from branch → `main` / root.
