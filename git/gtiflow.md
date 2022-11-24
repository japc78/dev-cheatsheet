---
title: "GtiFlow"
tags: ""
---

# Git Flow

Modo de trabajo

- [git-flow-cheatsheet](http://danielkummer.github.io/git-flow-cheatsheet/)
- [Introducción a GIT + Bitbucket + GIT-FLOW con un ejemplo práctico](https://youtu.be/tv1lZNogxyQ)

Inicializar git-flow

```bash
git flow init
```

## Notación (prefijos) para comentarios de acuerdo a Git-flow

- `feat:` Una nueva característica
- `fix:` Una corrección de error
- `docs:` Cambios en la documentación o en los comentarios(notar que el tipo es en plural 'docs')
- `style:` Cambios que no afectan el significado del código (espacios en blanco,  formateo, faltó un punto y coma, etc)
- `refactor:` Un cambio en el código que no corrige un error, ni agrega una  característica
- `test:` Agregando pruebas que falten(porque agregar nuevos test son considerados feat)
- `perf:` Cambio de código que mejora el rendimiento
- `revert:` rollback del commit 5050sad_istic
- `chore:` Cambios en el proceso de construcción(compilación) o herramientas auxiliares y/o bibliotecas como generadores de documentación
