# Ecosistema de Automatización IA para Negocios

Sistema que automatiza la generación, revisión humana y distribución de contenido para una consultora de automatización para pequeñas empresas.

## Stack tecnológico

- **Orquestador:** n8n
- **Base de datos:** Notion
- **Procesamiento IA:** OpenAI GPT-4o-mini
- **Canales:** Slack y Gmail

## Flujos implementados

### Workflow A — Generación y revisión
- Busca contenidos con estado `Pendiente` en Notion.
- Valida datos obligatorios.
- Clasifica el contenido con GPT-4o-mini.
- Recupera conocimientos desde Notion (RAG).
- Genera un borrador con fuentes.
- Guarda el borrador como `En revisión`.
- Notifica por Slack para revisión humana.

### Workflow B — Aprobación y envío
- Busca contenidos `Aprobados`.
- Valida aprobación, versión, aprobador y ausencia de envíos previos.
- Genera un identificador único de envío.
- Registra la ejecución en Notion.
- Envía el contenido por Gmail.
- Marca el contenido como `Publicado`.
- Cierra la ejecución como `Finalizada / Publicado`.

## Resiliencia
- Validación de datos antes de consumir IA.
- Control anti-duplicados mediante `Id envío`.
- Human-in-the-loop antes de la distribución.
- Rutas de error con registro en Notion.

## Documentación
- Documento final: TBD
- Dashboard de Control: https://app.notion.com/p/Dashboard-de-Control-Ecosistema-IA-3fd9ef1f77e7809b8a09f630832d01e9?source=copy_link
- Video demo: TBD
