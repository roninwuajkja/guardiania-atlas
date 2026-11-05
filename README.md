# IA Guardian · Atlas de arquitectura

Set de **70 diagramas HTML autónomos** para el proyecto **IA Guardian 1.7.3**, organizados en **7 módulos funcionales** y **10 tipos de lectura** por módulo.

**Sitio publicado:** <https://roninwuajkja.github.io/guardiania-atlas/>

Abre `index.html` para navegar todos los diagramas. Cada archivo HTML funciona sin servidor y conserva sus propios controles de tema y movimiento.

## Módulos

| # | Módulo | Qué cubre |
|---|---|---|
| 01 | Cuentas y autenticación | Registro, verificación, login, refresh rotatorio, consentimientos y auditoría del tutor. |
| 02 | Vinculación y dispositivos | QR corto o código manual, asentimiento del menor, activación, revocación y PIN de desvinculación. |
| 03 | Captura y privacidad | Listener, sanitizador, composición de ventanas y SQLCipher; el texto vive solo en memoria. |
| 04 | Sincronización y transporte | WorkManager, outbox cifrado, evaluación prioritaria, idempotencia y refresh del dispositivo. |
| 05 | Riesgo e IA | Reglas deterministas, cadena de proveedores, caché, circuit breaker y política de nivel mínimo. |
| 06 | Alertas y tiempo real | Persistencia, deduplicación, TutorHub, WebSocket en primer plano y FCM en segundo plano. |
| 07 | Panel y operación | Guardia de hoy, alertas, equipos, retención, barrido de sin señal y mantenimiento. |

## Las diez lecturas

| Tipo | Pregunta que responde |
|---|---|
| Arquitectura | ¿Qué componentes existen y qué fronteras cruzan? |
| Flujo | ¿Qué pasos sigue el proceso y qué ramas tiene? |
| Secuencia | ¿Quién llama a quién y en qué orden? |
| Datos | ¿De dónde salen los datos, cómo se transforman y dónde terminan? |
| Ciclo de vida | ¿Qué estados tiene una entidad y qué transiciones los cambian? |
| ERD | ¿Qué tablas, columnas, claves y relaciones existen? |
| Clases | ¿Qué tipos, contratos y dependencias sostienen el módulo? |
| Árbol | ¿Cómo se descompone el módulo en capacidades? |
| Timeline | ¿Qué ocurrió y cuánto tiempo pasó entre eventos? |
| Waterfall | ¿Dónde se va el tiempo dentro de una operación? |

## Estructura

```text
index.html
404.html
favicon.svg
01-cuentas-autenticacion/
  01-architecture.html
  02-workflow.html
  03-sequence.html
  04-dataflow.html
  05-lifecycle.html
  06-erd.html
  07-class.html
  08-tree.html
  09-timeline.html
  10-waterfall.html
...
```

Cada HTML es autocontenido: no necesita assets externos ni un servidor. El workflow de GitHub Actions copia solo los archivos del sitio a `_site` y publica con GitHub Pages.

## Publicación

El sitio se publica con **GitHub Actions → GitHub Pages**. Si el repositorio es privado, GitHub Pages requiere **GitHub Pro, Team o Enterprise**; si Pages no está habilitado, el workflow no puede desplegar.

Para publicar o republicar:

1. Ir a **Settings → Pages**.
2. Elegir **Source: GitHub Actions**.
3. Ejecutar el workflow **“Deploy Atlas to GitHub Pages”** o hacer push a `main`.

## Evidencia y alcance

- Código base: repositorio privado `roninwuajkja/guardiania`, revisión `b67d72dc67b107e6109ba363c46f78885d06e657`.
- Los diagramas de arquitectura, flujo, secuencia, datos, ciclo de vida, ERD, clases, árbol y waterfall están respaldados por rutas y líneas del repositorio cuando el render lo permite.
- Los timelines operativos están marcados como **ilustrativos**; los timelines de evolución usan fechas de tags, commits o registros del changelog y están marcados como **observados**.
- Los waterfalls son presupuestos ilustrativos, no trazas medidas. La única latencia documentada que se cita es la de Groq en la demo.
- Los ERD más densos usan el perfil `standard` para no sacrificar la visibilidad de todas las columnas; el resto usa `showcase`.

## Verificación

Los 70 HTML pasaron las cuatro compuertas automáticas de Archify: validación, entrega, chequeo estático y chequeo de navegador real en cuatro viewports. No se realizó una revisión visual perceptual humana de cada pieza.

## Privacidad

Los diagramas describen el diseño del sistema. No incluyen datos reales de menores, conversaciones, credenciales ni contenido de notificaciones.

> **Nota:** GitHub Pages publica el sitio en una URL pública. Los enlaces de fuente apuntan al repositorio privado `guardiania` y requieren acceso a la cuenta para abrirse. `robots.txt` pide a los buscadores no indexar el sitio.
