# 🚀 Guía Técnica Definitiva de Git y DevOps

Este documento técnico ha sido diseñado como una guía de consulta rápida y detallada sobre el uso de **Git**. Explica de forma clara y precisa la función, el propósito y el comportamiento interno de cada comando esencial utilizado en el flujo diario de desarrollo y automatización de despliegues (CI/CD).

---

## 💻 1. Configuración Inicial del Entorno
Estos comandos se ejecutan por única vez cuando se instala Git en un nuevo equipo o sistema operativo Linux. Establecen la identidad del desarrollador en cada línea de código.

* `git config --global user.name "Fernando Cajias"`
  * **¿Qué hace?** Registra tu nombre globalmente en el sistema.
  * **Comportamiento:** Cada cambio (*commit*) que realices llevará tu firma digital para que el equipo sepa quién introdujo las modificaciones.

* `git config --global user.email "fdv.cajias@yavirac.edu.ec"`
  * **¿Qué hace?** Vincula tus confirmaciones de código con tu correo electrónico institucional.
  * **Comportamiento:** Es indispensable para enlazar correctamente los accesos de tu computadora con tu cuenta web de GitHub.

---

## 📂 2. Creación e Inicialización de Proyectos

* `git init`
  * **¿Qué hace?** Convierte una carpeta común de tu computadora en un repositorio local de Git.
  * **Comportamiento:** Crea una carpeta oculta llamada `.git` donde el programa empezará a rastrear cada línea de código, cada archivo nuevo y cada eliminación que realices.

* `git remote add origin <URL_DEL_REPOSITORIO>`
  * **¿Qué hace?** Establece un puente de comunicación entre tu computadora local y el servidor en la nube de GitHub.
  * **Comportamiento:** La palabra `origin` funciona como un alias o atajo para no tener que escribir la dirección web completa del repositorio cada vez que se suban archivos.

---

## 🛠️ 3. El Flujo de Trabajo Diario (Guardado de Cambios)
Este ciclo de tres pasos es el que se ejecuta constantemente durante la jornada de desarrollo para registrar los avances de tus tareas.



* `git status`
  * **¿Qué hace?** Muestra una radiografía del estado actual de tu carpeta de trabajo.
  * **Comportamiento:** Te indica en color rojo los archivos que han sido modificados o creados y que aún no han sido preparados para guardarse, y en verde los que ya están listos.

* `git add .`
  * **¿Qué hace?** Prepara todos los archivos modificados y nuevos, agregándolos al área de preparación (*Staging Area*).
  * **Comportamiento:** El punto (`.`) representa a todo el directorio actual. Es el equivalente a colocar todos tus documentos dentro de la caja de envío, listos para ser sellados.

* `git commit -m "Mensaje descriptivo del cambio"`
  * **¿Qué hace?** Guarda de forma definitiva los cambios en el historial de tu computadora local, sellando la versión con un mensaje descriptivo.
  * **Comportamiento:** Crea un punto de control en la historia del proyecto. Si en el futuro algo falla, puedes regresar exactamente al momento en que generaste este *commit*.

---

## 🔌 4. Sincronización y Despliegue (Conexión con la Nube)

* `git push origin main`
  * **¿Qué hace?** Envía y sube todos los *commits* guardados en tu computadora hacia el repositorio remoto en GitHub.
  * **Comportamiento:** Actualiza el servidor web con tu código más reciente. En entornos de DevOps, este comando suele disparar automáticamente los pipelines de GitHub Actions.

* `git pull origin main`
  * **¿Qué hace?** Descarga e integra las últimas modificaciones que existan en GitHub directamente a tu computadora local.
  * **Comportamiento:** Es fundamental usarlo si editaste archivos directamente desde la página web o si estás trabajando en equipo, asegurando que tu entorno local esté perfectamente actualizado.

* `git branch -M main`
  * **¿Qué hace?** Fuerza el renombre de la rama por defecto de tu proyecto local a "main".
  * **Comportamiento:** Garantiza el cumplimiento de los estándares modernos de desarrollo, ya que versiones antiguas de Git inicializaban la rama principal con el nombre obsoleto de "master".

* `git push -u origin main --force`
  * **¿Qué hace?** Sobrescribe de forma obligatoria el historial del repositorio remoto en GitHub con el historial que posees en tu computadora.
  * **Comportamiento:** Se utiliza únicamente en situaciones de emergencia o configuraciones iniciales conflictivas, como cuando el repositorio web contiene descripciones o archivos iniciales automáticos que bloquean una sincronización limpia.

---

> ⚠️ **Regla de Oro para DevOps:** Nunca realices un `git push --force` en proyectos empresariales donde múltiples desarrolladores compartan la misma rama, ya que podrías borrar de forma irreversible el trabajo de tus compañeros. Úsalo con extrema precaución y solo en laboratorios o ramas individuales.

---
