---
name: markdown-docs
description: Use when creating or editing any module, certification guide, or lab in this DevOps program. Enforces consistent structure, formatting, and technical writing standards across all Markdown files.
---

# Markdown Documentation Skill

## Estructura estándar de un módulo

Todo módulo debe seguir esta estructura exacta (en este orden):

```markdown
# Módulo XX — Nombre del módulo

> Descripción de una línea sobre el propósito del módulo.

---

## Objetivos del módulo
## Competencias a desarrollar
## Tiempo estimado
## Prerrequisitos
## Recursos oficiales
## Recursos complementarios
## Plan de estudio semanal
## Laboratorios
## Proyecto práctico
## Checklist
## Preparación para la certificación (si aplica)
## Referencias
```

## Reglas de formato

### Bloques de código
Siempre especificar el lenguaje:
- Shell/Bash: ` ```bash `
- YAML: ` ```yaml `
- Terraform/HCL: ` ```hcl `
- JSON: ` ```json `
- Python: ` ```python `
- Texto plano / output: ` ```text `
- Markdown: ` ```markdown `

### Tablas
- Primera columna alineada a la izquierda
- Columnas de estado centradas
- Columnas de texto a la izquierda
- Siempre incluir fila de encabezado y separador

```markdown
| Dominio | Peso | Estado |
|---------|------|:------:|
| Cluster Architecture | 25% | ⏳ |
```

### Checkboxes
- Tarea pendiente: `- [ ] Descripción`
- Tarea completada: `- [x] Descripción`
- No usar `* [ ]` ni `+ [ ]`

### Notas y advertencias
```markdown
> ℹ️ Nota informativa

> ⚠️ Advertencia importante

> ❌ Error común a evitar
```

### Secciones de laboratorio
Cada lab debe tener:
1. **Objetivo** — qué demuestra este lab
2. **Prerrequisitos** — qué debe estar disponible
3. **Pasos** — comandos numerados y verificables
4. **Verificación** — cómo confirmar que funcionó
5. **Limpieza** — cómo deshacer si aplica

```markdown
### Lab XX-01: Nombre del laboratorio

**Objetivo:** Demostrar X en contexto Y.

**Prerrequisitos:**
- Cluster kubeadm corriendo
- kubectl configurado con acceso admin

**Pasos:**

1. Crear el recurso:
   ```bash
   kubectl apply -f manifests/ejemplo.yaml
   ```

2. Verificar estado:
   ```bash
   kubectl get pods -n default
   ```

**Verificación esperada:**
```text
NAME          READY   STATUS    RESTARTS   AGE
ejemplo-pod   1/1     Running   0          30s
```

**Limpieza:**
```bash
kubectl delete -f manifests/ejemplo.yaml
```
```

## Convenciones de escritura

- Escribir en español
- Oraciones cortas, activas, sin rodeos
- Los nombres de herramientas van en backtick inline: `kubectl`, `ArgoCD`, `Vault`
- Los nombres de archivos van en backtick: `AGENTS.md`, `opencode.json`
- Las rutas van en backtick: `.opencode/skills/`
- Las variables de entorno van en MAYÚSCULAS y backtick: `$KUBECONFIG`
- No usar emojis en encabezados de sección
- Los íconos de estado (✅ ⏳ ❌) solo en tablas y checklists, nunca en prosa

## Densidad de contenido

- Un módulo completo: 300-800 líneas de Markdown
- Un lab: 30-80 líneas
- Una guía de certificación: 150-400 líneas
- Si supera 800 líneas, dividir en sub-secciones con archivos separados en un subdirectorio
