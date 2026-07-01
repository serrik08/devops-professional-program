# AGENTS.md — DevOps Professional Program

## Contexto del proyecto

Este repositorio es un programa de formación profesional de 12 meses para consolidar un perfil DevOps Senior / Platform Engineer / SRE. No es un proyecto de código — es documentación técnica estructurada en Markdown.

**Autor:** Sergio Ricardo Gerónimo Rocha  
**Stack actual (contexto real):** AWS EKS 1.35 arm64 · ArgoCD v2.14 · Terraform · Vault 0.29.1 · Istio 1.25 · Karpenter · External Secrets · Crossplane · VictoriaMetrics · Loki

## Reglas estrictas para el agente

### Estructura de archivos
- Todos los módulos van en `modules/` con prefijo numérico: `05-kubernetes-cka.md`
- Todas las guías de certificación van en `certifications/`
- Los laboratorios van en `labs/<nombre-modulo>/`
- Los proyectos van en `projects/<nombre-proyecto>/`
- Nunca crear archivos fuera de estas carpetas sin confirmación explícita

### Estilo de documentación
- Escribir en español (el programa es personal, no público aún)
- Markdown limpio — sin HTML embebido
- Los bloques de código deben tener el lenguaje especificado: ```bash, ```yaml, ```hcl, etc.
- Las tablas deben tener alineación consistente
- Los checkboxes de tareas usan `- [ ]` y `- [x]`

### Contenido técnico
- Priorizar documentación oficial sobre blogs de terceros
- Cuando se mencionen versiones de herramientas, usar las que corresponden al stack real del autor (ver arriba)
- Los laboratorios deben ser ejecutables en WSL Ubuntu o sobre AWS plat-dev (EKS)
- No inventar comandos — si hay duda, documentar el comando con una nota de verificación

### Módulo de Kubernetes (05-kubernetes-cka.md)
Este módulo es el más crítico del programa (CKA pesa ~$445 y el examen es hands-on).
- Incluir los 5 dominios oficiales del examen con sus pesos exactos
- Los labs deben usar `kubeadm` (no EKS) para preparar el entorno del examen
- Incluir siempre la sección de alias y shortcuts de kubectl
- Referenciar los hallazgos H-01 a H-05 de la migración real como material de troubleshooting

### PROGRESS.md
- Nunca sobrescribir semanas ya completadas
- Solo agregar nuevas semanas al final del archivo
- El formato del template semanal es fijo — no modificarlo

### CHANGELOG.md
- Seguir formato: `## vX.Y — YYYY-MM` + lista de cambios
- Incrementar versión minor para nuevos módulos, patch para correcciones

## Agentes disponibles

Usá `Plan` (Tab) para revisar estructura antes de escribir.  
Usá `Build` para generar o editar contenido de módulos.

## Comandos custom disponibles

- `/new-module <nombre>` — crea un nuevo módulo con estructura estándar
- `/new-lab <modulo> <nombre>` — crea un nuevo laboratorio en la carpeta correcta
- `/weekly` — agrega la entrada de seguimiento semanal a PROGRESS.md
- `/review-module <archivo>` — revisa consistencia de formato y contenido de un módulo

## Lo que NO debe hacer el agente sin confirmación

- Eliminar o sobreescribir módulos existentes
- Cambiar la estructura de carpetas definida en README.md
- Agregar dependencias externas o scripts ejecutables fuera de `scripts/`
- Modificar PROGRESS.md en semanas ya registradas
