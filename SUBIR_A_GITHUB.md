# Cómo publicarlo (5 minutos)
1. En github.com → **New repository** → nombre `gcp-finanzas` → **Public** → Create.
2. Sube los archivos (arrastrando en "uploading an existing file") o desde terminal, con varios commits para tener historial:
```
git init && git branch -M main
git add README.md && git commit -m "docs: README del desafio"
git add index.html .nojekyll && git commit -m "feat: dashboard GCP con tres escenarios y modulo QA"
git remote add origin https://github.com/TU-USUARIO/gcp-finanzas.git
git push -u origin main
```
3. **Settings → Pages → Source: Deploy from a branch → main / (root) → Save.**
4. En ~1 minuto cualquiera verá la página en `https://TU-USUARIO.github.io/gcp-finanzas/`. Pon ese enlace en el README y entrégalo junto al enlace del repo.
