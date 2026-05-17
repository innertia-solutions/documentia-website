# Documentia — Documentación base del producto

> Última revisión: 2026-05-16
>
> **V1** — Gestión documental + cumplimiento + copiloto IA de auditoría + AI Workspace corporativo
> **V2** — Documentia como proxy de IA corporativa con tokenización de entidades sensibles *(visión)*

---

## Qué es

Documentia es una plataforma de gestión documental y cumplimiento con IA para empresas que se auditan bajo normas ISO y SGI.

No es un gestor de archivos. No es un chat con documentos. Es la plataforma que centraliza, gobierna y analiza los documentos críticos de la empresa — y que usa IA para detectar brechas, preparar auditorías y proteger la información corporativa.

La IA es el eje principal, no una feature adicional.

---

## Propuesta de valor

> Tu programa de cumplimiento, siempre listo.

Documentia convierte tus auditorías en un programa vivo — con historial, comparación entre ciclos y un copiloto que detecta brechas antes de que llegue el auditor.

Aliviana el trabajo del área de calidad y cumplimiento. Elimina la preparación a última hora.

---

## Problema que resuelve

Las empresas que se auditan (ISO, SGI, auditorías de clientes, fiscalizaciones) tienen dos problemas recurrentes:

**1. Caos documental:**
- Documentos repartidos en Drive, correos, WhatsApp, planillas y sistemas internos
- Nadie sabe cuál es la versión vigente
- Sin evidencia ordenada cuando llega el auditor
- Preparación de auditorías en los días previos, a las carreras

**2. IA sin control:**
- Los empleados usan ChatGPT u otras IAs públicas para trabajar con documentación
- Pegan información confidencial en sistemas externos sin saberlo
- La empresa no tiene visibilidad ni control sobre qué información cruza hacia la IA
- No hay trazabilidad de qué se consultó, con qué contexto, ni quién lo hizo

---

## Enfoque

**IA como eje central.** La plataforma entiende tus documentos, tus normas y tus procesos, y actúa como un copiloto que te guía hacia el cumplimiento y protege la información corporativa.

**Tres pilares del producto:**

### 1. Controla
Repositorio central con versión vigente, responsable, estado, vencimiento y relación con normas o procesos. Clasificación de confidencialidad incorporada desde el inicio.

### 2. Evidencia
Reúne y organiza todo lo que demuestra cumplimiento: registros, fotografías, actas, certificados, inspecciones, checklists, aprobaciones — vinculados a procesos, requisitos y auditorías.

### 3. Audita y trabaja con IA
El copiloto detecta brechas antes de que llegue el auditor. El AI Workspace permite a todos los empleados trabajar con IA, pero usando solo información autorizada por la empresa, con log completo de todo lo que se procesa.

---

## Público objetivo

**Empresa ideal:** Grandes empresas industriales chilenas con múltiples certificaciones (ISO 9001, 14001, 45001, SGI), auditorías recurrentes y equipos de calidad que hoy trabajan con carpetas, planillas y correos.

**Sectores:** agroindustria, alimentos, logística, minería, manufactura, construcción, servicios industriales, proveedores de grandes empresas.

**Usuarios:**
- **Documentia Core:** Jefe de Calidad, Encargado de SGI, Gerente de Cumplimiento, equipo de auditoría interna
- **AI Workspace:** todos los empleados que necesiten trabajar con documentación e IA (operadores, vendedores, supervisores, administración)

---

## Módulos del producto

### 🗂 1. Repositorio Documental
- Carga y almacenamiento de documentos (PDF, Word, Excel, imágenes, XML)
- Control de versiones con historial completo
- Responsable, fecha de revisión y estado por documento
- Bloqueo de documentos aprobados (no editables sin flujo de revisión)
- Clasificación: público, interno, confidencial, restringido
- Búsqueda y filtros por proceso, norma, área, estado
- Alertas automáticas de vencimiento

### ✅ 2. Cumplimiento Normativo
- Matriz de cumplimiento ISO 9001, 14001, 45001, SGI, etc.
- Requisitos y cláusulas vinculados a documentos y evidencias
- Estado de cumplimiento en tiempo real por cláusula
- Asignación de responsables por requisito
- Alertas de incumplimiento y documentos vencidos

### 📎 3. Gestión de Evidencia
- Registro de evidencias (fotos, actas, certificados, registros)
- Vinculación de evidencia a procesos, auditorías y requisitos
- Trazabilidad completa: qué evidencia respalda qué cumplimiento
- Estado de validación por evidencia

### 📋 4. Programas de Auditoría
- Definición de programas normativos (marco siempre activo)
- Campañas por tipo y período (pre-auditoría, interna, externa)
- Kanban de ejecución con estados por requisito
- Adjunto de evidencia por ítem de auditoría
- Score de cumplimiento al cierre de campaña
- Hallazgos y no conformidades con responsable y fecha
- Comparativa entre ciclos (cláusula vs cláusula, período vs período)
- Exportación de índice documental y reportes para el auditor

### 🤖 5. Copiloto IA de Auditoría
- Análisis del repositorio contra requisitos de certificación
- Detección automática de brechas y documentos vencidos
- Checklist de preparación pre-auditoría
- Consulta en lenguaje natural ("¿qué falta para ISO 9001 cláusula 8?")
- Generación de reportes exportables

### 🔐 6. AI Workspace Corporativo
Permite a todos los empleados usar IA para trabajar con documentación, pero bajo control total de la empresa.

**Gobernanza bidireccional:**

```
→ Entrada:  el empleado sube un doc al chat
            → Documentia lo escanea contra las clasificaciones del repositorio
            → si es confidencial/restringido: bloquea y avisa al empleado
            → log del intento (quién, qué doc, timestamp)

← Salida:   la IA responde usando solo el corpus autorizado
            → log completo: qué preguntó, qué documentos usó la IA, respuesta
```

**Funcionalidades:**
- Chat de IA para empleados con contexto controlado por la empresa
- Administrador marca qué documentos están autorizados para uso con IA
- Clasificación automática al ingresar documentos (Opción C):
  - **Fase 1:** reglas basadas en clasificación ya existente en Documentia (instantáneo)
  - **Fase 2:** clasificación IA automática como fallback para docs no clasificados
- Bloqueo y aviso cuando un documento ingresado es confidencial o restringido
- Acciones disponibles: consultar, redactar, resumir, comparar, rellenar plantillas
- Corpus aislado por empresa (multi-tenant)
- Roles: admin configura corpus autorizado / empleado solo usa el chat

**Por qué es diferente a ChatGPT:**
- La empresa define qué información puede procesar la IA
- Nada confidencial sale a sistemas externos sin pasar por los filtros
- Todo queda logueado y auditado
- La empresa se hace responsable de lo que cruza — y tiene el control para hacerlo

### 👥 7. Roles y Permisos
- Roles base: Administrador, Gestor Documental, Auditor, Empleado, Solo lectura
- Permisos granulares por módulo y por documento
- Control de quién puede marcar documentos como autorizados para IA
- Gestión de acceso al AI Workspace por área o rol

### 📊 8. Dashboard y Reportes
- Vista general: documentos vigentes, vencidos, en revisión
- Estado de cumplimiento por norma y por área
- Actividad reciente del equipo
- Reportes exportables (PDF/Excel): índice documental, estado de auditoría, log de IA

### 🔔 9. Notificaciones y Alertas
- Vencimientos próximos de documentos
- Documentos sin responsable o sin revisión
- Brechas detectadas por el copiloto
- Intentos de procesar documentos confidenciales en el AI Workspace
- Notificaciones por email y en-app

### 🔌 10. Integraciones
- **DocuSeal** — firma electrónica de documentos
- **Google Drive / OneDrive** — ingesta de documentos desde la nube
- **API REST** — para conectar con sistemas internos (ERP, HRIS)
- **Webhooks** — eventos en tiempo real para integraciones externas
- SSO / OAuth para autenticación corporativa

### 🏛 11. Infraestructura y Seguridad
- Multi-tenancy con aislamiento de datos por empresa
- Almacenamiento cifrado en reposo y en tránsito
- Auditoría completa de eventos (quién hizo qué, cuándo, desde dónde)
- Exportación del log de auditoría (defendible ante un auditor externo)
- Control de retención de datos

---

## Diferenciadores

| Vs. | Documentia |
|---|---|
| Google Drive | Drive guarda archivos. Documentia demuestra cumplimiento. |
| Notion | Notion organiza wikis. Documentia controla versiones, evidencia y brechas de auditoría. |
| Gestores documentales tradicionales | Almacenan. Documentia analiza, detecta riesgos y te dice qué falta. |
| ChatGPT / Claude público | Cualquier empleado puede filtrar información confidencial. Documentia controla qué puede y no puede procesar la IA — con log completo. |
| RAG genérico | Sin gobernanza de datos, sin auditoría, sin clasificación de confidencialidad. |

---

## Posicionamiento

Documentia no es "chat con documentos".
Documentia no es un gestor de archivos con IA pegada.
Documentia no es ChatGPT para empresas.

Documentia es:
> **La plataforma que gobierna tus documentos y tu IA corporativa — para que la empresa cumpla y no improvise.**

---

## Fuera del scope (V1)

- Generación de minutas de reunión (integración posible con Granola, Diio)
- Firma electrónica propia (integración con DocuSeal)
- ERP o gestión de procesos operacionales
- Formación y capacitación online

---

## Visión V2 — Documentia como proxy de IA corporativa

> *Esta sección describe la dirección de largo plazo del producto, no el scope de V1.*

### El problema que resuelve

Hoy cuando un empleado usa ChatGPT o Claude directamente:

```
Empleado → "Analiza el proyecto Copayapu de Colbún, 450MW, flujo X..."
               ↓
           Anthropic recibe: propietario + datos + contexto completo
```

El proveedor de IA conoce quién es el cliente, cuál es el proyecto, cuáles son los datos operacionales. Si hay un incidente de seguridad, si los datos se usan para entrenamiento, o si hay una filtración — la empresa expuso su información más sensible sin saberlo.

### La solución: tokenización de entidades como middleware

Documentia actúa como proxy entre los empleados y la IA. Antes de enviar cualquier prompt a Claude, una capa de anonimización reemplaza las entidades sensibles por tokens neutros:

```
Empleado → Documentia → [Capa de tokenización]
                             ↓
"Proyecto Copayapu, cliente Colbún, 450MW"
   → "Proyecto [P-001], cliente [C-004], [VAL-01]"
                             ↓
                         Claude API
                             ↓
Respuesta con tokens → Documentia de-tokeniza → Empleado ve contexto real
```

Anthropic procesa la lógica del negocio — nunca conoce al propietario.

### Por qué Documentia es el lugar natural para esto

El repositorio documental ya contiene el diccionario de entidades sensibles de la empresa: clientes, proyectos, operaciones, códigos internos. No hay que construir esa base desde cero — Documentia ya la tiene, clasificada y gobernada.

### Arquitectura por fases

| Fase | Qué hace | Cuándo |
|---|---|---|
| **Fase 1** (V1 AI Workspace) | Bloquea documentos confidenciales antes de llegar a la IA | V1 |
| **Fase 2** (V2 early) | Tokenización de entidades del diccionario Documentia antes de cada prompt | V2 |
| **Fase 3** (V2 full) | NER dinámico: detecta entidades sensibles aunque no estén en el diccionario | V2 |

### Casos de uso V2

- Ingenieros actualizan proyectos y consultan a la IA sobre datos técnicos sin exponer cliente ni operación
- Área comercial usa IA para analizar propuestas sin que el proveedor sepa de qué cliente se trata
- RRHH consulta a la IA sobre casos de personas sin exponer identidades
- La empresa puede certificar ante auditores que ningún dato propietario identificable salió hacia proveedores externos de IA

### El argumento de compliance

> "Anthropic no sabe que ese proyecto es de Colbún. Solo sabe que hay un [P-001] con [VAL-01]. El dato calculable viaja. El propietario se queda."

Para empresas en industrias reguladas (minería, energía, salud, finanzas), esto pasa de ser una ventaja competitiva a un requisito de operación.

### Lo que es difícil (honestidad técnica)

- Referencias implícitas no tokenizables ("el proyecto que firmamos el año pasado")
- Inferencias de Claude a partir de datos técnicos muy específicos de industria
- Información sensible emergente por combinación de datos aparentemente inocuos
- Requiere que las entidades estén bien clasificadas en Documentia para funcionar bien

Estos son problemas resolubles progresivamente — no bloqueantes para lanzar V2 en fases.
