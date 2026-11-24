# Sistema Gestión Ficticia — Repo de Práctica Git y VSCode

¡Bienvenida! Este repositorio es un entorno de práctica ficticio para que te amigues con **Git** y **VSCode** sin miedo a romper nada real.

Acá vas a trabajar con un proyecto de gestión inventado: listados de clientes, precios, configuración de ambientes (`QA` vs `Produccion`) y un bot de calendario.

## Consignas de práctica (en orden)

1. **Abrir el repo en VSCode y reconocer el panel de Source Control, el explorador y la terminal integrada.**
   Abrí la carpeta `repo-gestion` en VSCode. Ubicá el **Explorador** (archivos), el panel de **Source Control** (cambios, stage, commit, ramas y conflictos) y abrí la **Terminal integrada** (`Ctrl + ñ` o desde el menú superior) usando Git Bash.

2. **Ver el historial de cada rama y entender las diferencias (`git log --oneline --graph --all`).**
   Corré `git log --oneline --graph --all` en la terminal integrada. Mirá cómo se abren y avanzan las ramas `master`, `dev` y `soporte` a partir de la base común.

3. **Criterio de ramas: "llegó un bug urgente de un cliente, ¿en qué rama trabajás y por qué?"**
   Pensá y anotate tu respuesta antes de tocar código: ¿irías directo a `master`, trabajarías en `soporte` (o una rama de soporte/fix) y luego llevarías el arreglo a donde corresponda? Explicá qué representa cada rama en este flujo.

4. **Crear una rama propia a partir de dev, hacer un cambio y un commit con buen mensaje.**
   Pasate a `dev`, creá una rama nueva con tu nombre o tarea (por ejemplo `feat/mejora-precios` o `fix/tu-nombre`), editá algún archivo, hacé `git add` y `git commit` con un mensaje claro en español (en tiempo presente o imperativo, describiendo qué y para qué).

5. **Resolver el conflicto 1 (`dev -> master`) usando el editor de conflictos de VSCode.**
   El archivo `src/precios.txt` tiene cambios en las mismas líneas en `master` y en `dev`. Intentá mergear `dev` dentro de `master`, abrí `src/precios.txt` en VSCode, usá las opciones del editor de conflictos (*Accept Current*, *Accept Incoming*, *Accept Both* o editá a mano), guardá, hacé `add` y completá el commit del merge.

6. **Resolver el conflicto 2 (`soporte -> dev`).**
   El archivo `src/clientes.txt` tiene cambios en las mismas líneas en `dev` y en `soporte`. Pasate a `dev`, mergeá `soporte`, resolvé el conflicto en `src/clientes.txt` y cerrá el commit de merge.

7. **Cargar al repo los archivos de `escritorio-simulado/` (`add`, `commit`, `push`) sin ayuda de IA.**
   Afuera del repo (al lado de `repo-gestion`), tenés la carpeta `escritorio-simulado/` con tres archivos sueltos. Copiá los que correspondan adentro de `repo-gestion` (por ejemplo en `src/`), hacé `add`, `commit` y `push` vos sola, sin pedirle el comando a una IA.

8. **Escenario `dev -> soporte`: `stash`, cambiar de rama, cargar `src/bot-calendario.txt` en `soporte`, volver a `dev` y recuperar el `stash`.**
   Estando en `dev` vas a ver cambios sin commitear (working directory sucio) y un archivo `bot-calendario.txt` esperando en `escritorio-simulado/`. Hacé `git stash` para guardar tu trabajo a medias, cambiate a `soporte`, copiá `escritorio-simulado/bot-calendario.txt` a `repo-gestion/src/bot-calendario.txt`, hacé `add` y `commit` en `soporte`, volvé a `dev` y recuperá tus cambios con `git stash pop`.

9. **Leer los dos `appsettings` y explicar con tus palabras qué es producción y qué es QA, y por qué tocar QA no afecta a ningún cliente.**
   Abrí `config/appsettings.QA.json` y `config/appsettings.Produccion.json`. Compará servidores y nombres de base (`gestion_qa` vs `gestion_prod`) y explicá con tus palabras qué es cada ambiente y por qué probar o tocar `QA` no impacta en los clientes reales.
