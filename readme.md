# SimpleMarcas — Google Apps Script (copia editable en VS)

## Qué es esto
Este repositorio contiene una **copia editable** del código de **Google Apps Script** que ya está **online** (deployado como Web App).
**Importante:** el código que está corriendo en producción vive en Google Apps Script (Google Sheet / Apps Script).  
Este repo es el lugar donde **Codex puede editar** el código con comodidad.

## Fuente de verdad (Source of truth)
- **Producción (online):** Google Apps Script (Web App deployada)
- **Copia editable para modificar con Codex:** `apps-script/Code.gs`

**Regla:** Codex puede cambiar `apps-script/Code.gs`, pero esos cambios **NO quedan online automáticamente**.  
Yo (humano) haré el paso manual: **copiar/pegar** desde `apps-script/Code.gs` hacia el editor de Apps Script y luego **redeploy**.

## Flujo de trabajo (muy importante)
1. Codex modifica: `apps-script/Code.gs`
2. Yo copio y pego el contenido actualizado dentro de Google Apps Script (en el Google Sheet)
3. Yo hago **Deploy** (o “Manage deployments” → “Edit” → “Deploy”) para que los cambios queden online

## Carpetas relevantes
- `apps-script/Code.gs`  
  Copia editable del código de Apps Script (la que Codex debe modificar).
- (Opcional) `frontend/`  
  Si hay front-end (HTML/JS), vive acá. No mezclar lógica de Apps Script en el front.

## Instrucciones para Codex (IA)
Cuando edites `apps-script/Code.gs`:
- Asume que este archivo es una **copia espejo** del código online.
- No digas “ya quedó deployado” o “ya quedó en producción”.
- Siempre recuerda en tus respuestas: **“falta copiar/pegar a Apps Script y redeploy”**.
- No cambies nombres de endpoints, `doGet/doPost`, `mode`, nombres de hojas, columnas o contratos de respuesta,
  a menos que el usuario lo pida explícitamente.
- Mantén el código lo más compatible posible con Google Apps Script (sin imports de Node, sin dependencias externas).

## Datos del deploy (rellenar)
- Web App URL (producción): <PEGAR_URL_AQUI>
- Spreadsheet ID (si aplica): <PEGAR_ID_AQUI>
- Timezone esperada: <PEGAR_TZ_AQUI>

## Notas rápidas de Apps Script
- El entorno es Google Apps Script (V8).
- Si hay cambios de permisos/Scopes, al pegar en Apps Script puede pedir reautorizar.
