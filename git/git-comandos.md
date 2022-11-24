# Comandos básicos

- `git branch` Lista las ramas del repositorio.
- `git checkout -b` <nombre_rama> Crea una nueva rama y te cambia a ella.
- `git branch <nombre_rama>` Crea una nueva rama y te mantiene en ella (gracias Julian Alejandro Sosa).
- `git checkout <nombre_rama>` Te cambia de rama.
- `git checkout` - cambia del actual branch al anterior branch en el que hubieran estado
- `git show-branch` Muestra las ramas que existen y cual ha sido su historia.
- `git show-branch all` Similar a la anterior pero con mas datos.
- `git rebase <nombre_rama>` Hace un rebase (se conservan todos los commit de la rama diferida sobre la rama master. Gracias Alejandro Gonzáles Reyes).
- `git merge <nombre_rama>` Hace un merge (merge es fusionar todos los commit de una rama sobre otra en un solo punto, merge no elimina en automático la rama, esta hay que eliminarla manualmente. Gracias Alejandro Gonzáles Reyes).
- `git add .` Añade todos los cambios de la carpeta actual al siguiente commit.
- `git status` Permite saber que archivos y cuales no fueron agregados al escenario.
- `git show`. Muestra todos los cambios que se han realizado, incluye las lineas que hemos cambiado, cuando y quien realizó los cambios
- `git log` Historial completo del archivo
- `git log --oneline --graph --all`. Historial de una forma grafica, mas entendible.
- `git push` Envía los cambios al repositorio remoto
- `git pull` Agrega los cambios del commit más nuevo al repositorio local
- `gitk` ver gráficamente nuestro entorno y flujo de trabajo local
