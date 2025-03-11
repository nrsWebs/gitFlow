# Git Workflow Automation Script

## Descripción
Este script de Bash automatiza el flujo de trabajo de Git para la gestión de ramas en un proyecto de desarrollo. Permite la creación y finalización de features y hotfixes, así como la implementación de cambios en entornos de staging y producción.

## Requisitos
- Tener `git` instalado y configurado.
- Estar dentro de un repositorio de Git.
- El repositorio debe estar en `src/.git` dentro del directorio actual.

## Uso
El script proporciona los siguientes comandos:

### 1. **Feature Branch**
#### Crear una nueva feature branch:
```sh
./script.sh start.feature nombre-de-la-feature
```
#### Finalizar una feature branch:
```sh
./script.sh end.feature nombre-de-la-feature
```

### 2. **Hotfix Branch**
#### Crear una nueva hotfix branch:
```sh
./script.sh start.hotfix nombre-del-hotfix
```
#### Finalizar una hotfix branch:
```sh
./script.sh end.hotfix nombre-del-hotfix
```

### 3. **Deploy a Staging**
```sh
./script.sh deploy.pre nombre-de-la-rama
```
Este comando fusiona la rama especificada en `stg` y permite hacer un push a origen.

### 4. **Deploy a Producción**
```sh
./script.sh deploy.pro nombre-de-la-rama
```
Este comando realiza:
1. Merge en `develop` y push a origen.
2. Pregunta si se debe actualizar `master`.
3. Realiza el merge de `develop` en `master` y push a origen.
4. Pregunta si se debe eliminar la rama de la tarea.

## Funcionalidades Destacadas
- Uso de colores para resaltar los mensajes de entrada del usuario:
  - **Rojo ([31m)**: Preguntas de confirmación.
  - **Amarillo ([33m)**: Indicadores visuales de merge.
- Automatización de merges y tags.
- Confirmaciones interactivas antes de realizar operaciones críticas como `push` o `branch -D`.

## Notas
- Asegúrate de tener los permisos necesarios en el repositorio remoto antes de ejecutar los comandos.
- Las confirmaciones interactivas requieren entrada manual, por lo que el script no es completamente automático.

## Autor
Este script fue desarrollado para mejorar la gestión de flujos de trabajo en Git mediante Bash.

