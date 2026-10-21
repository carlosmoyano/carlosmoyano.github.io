# Hub central (Jekyll · jekyll-theme-hacker)

Página principal que enlaza a otras páginas de GitHub Pages (cursos, laboratorios, proyectos…).
Cada curso puede usar **su propio tema de Jekyll**: este hub solo los enlaza.

## Añadir un curso o proyecto nuevo
Edita `_data/projects.yml` y copia un bloque:

```yaml
- title: "Nombre del curso"
  description: "Qué se aprende en una frase."
  url: "https://TU_USUARIO.github.io/mi-curso/"
  status: "en-curso"        # en-curso | completado | proximamente
  progress: 30              # opcional, 0-100
  tags: [Python, Linux]
```
Para una categoría nueva, añade otro bloque `- id / icon / title / description / items`.

## Publicar
1. Edita `_config.yml` (título, usuario de GitHub, `portfolio_url`…).
2. Crea el repo **`TU_USUARIO.github.io`** y sube estos archivos:
   ```bash
   git init && git add . && git commit -m "Hub central"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_USUARIO.github.io.git
   git push -u origin main
   ```
3. **Settings → Pages → Deploy from a branch → `main` / `(root)`**.

## Cómo encajan las URLs
Este repo se llama **`TU_USUARIO.github.io`** y es la página principal. El resto cuelga de ahí:

| Repo | Dirección |
|---|---|
| `TU_USUARIO.github.io` | `https://TU_USUARIO.github.io/` (este hub) |
| `portfolio` | `https://TU_USUARIO.github.io/portfolio/` |
| `curso-python` | `https://TU_USUARIO.github.io/curso-python/` |
| `curso-virtualizacion` | `https://TU_USUARIO.github.io/curso-virtualizacion/` |

Cada repo se publica con **Settings → Pages → `main` / `(root)`** y puede usar su propia plantilla de Jekyll.
En cada uno, pon en su `_config.yml` `baseurl: "/nombre-del-repo"`.

## Probar en local
```bash
bundle install && bundle exec jekyll serve   # http://localhost:4000
```
