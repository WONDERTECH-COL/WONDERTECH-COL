**El README.md debe incluir (mínimo):**

- Flujo del proceso (pasos + diagrama Mermaid)
- Cómo ejecutar/instalar (si aplica)
- Criterios de QA / definición de “listo para entrega”

---

## 4) Flujo oficial A (sin PR): Dev → QA → Empresa

Este flujo se usa cuando el desarrollo inicia en el repo personal del desarrollador y luego se entrega a la empresa.

### 4.1 Principio

- Cada desarrollador trabaja en su **repositorio personal**.
- La entrega se vuelve “oficial” cuando el repositorio queda en la **organización/cuenta de la empresa**.

### 4.2 Pasos (checklist)

1. **PM** registra/valida el **ID** en Odoo y define el nombre estándar del repo.
2. **Dev** crea el repo en su cuenta con el nombre: `[ID]_NOMBRE_PROYECTO`.
3. **Dev** mantiene estructura (`/documentacion`, `/proyecto`) y actualiza README.
4. Si se requiere, **Dev invita a QA y PM** como colaboradores (para revisión).
5. **QA** valida versión candidata.
6. Si QA aprueba: **Dev crea Release/Tag** `vX.Y.Z` con notas.
7. **Dev transfiere** el repositorio a la organización/cuenta de la empresa.
8. **PM** registra la entrega en Odoo: link + versión/tag + evidencia QA.

---

## 5) Control de calidad (obligatorio) en flujo sin PR

Como no hay PR, el control se hace por **versiones entregables**.

**Regla: ninguna entrega es válida si NO tiene:**

- **Tag/Release** de versión `vX.Y.Z` + notas de entrega
- **Evidencia QA** en `documentacion/QA.md` (checklist + resultado + fecha)

---

## 6) “Compartir al repo de la empresa” (elige un estándar)

Se permiten dos opciones. La empresa debe escoger **una** como estándar.

### Opción A (recomendada): Transferencia del repositorio

- Tras QA aprobado, el Dev **transfiere** el repo a la organización.
- Ventaja: queda el historial completo intacto.

### Opción B: Repo empresa vacío + push por Git

- PM crea repo vacío en la organización con el nombre estándar.
- Dev agrega el repo como remote y hace push.
- Útil si la política interna no permite transferir repos, pero requiere disciplina.

---

## 7) Flujo oficial B (con PR): Upstream + Fork + Integrador

Este flujo se usa cuando se quiere control formal por PR, usando permisos y proceso.

### 7.1 Reglas obligatorias del repositorio oficial (Upstream)

- Nadie trabaja directamente en el repo oficial.
- Todo cambio entra por **Pull Request (PR)** desde un **fork personal**.
- Nadie hace merge de su propio PR.
- Existe un **Integrador semanal** (rotativo) y **solo esa persona** tiene permiso **Write** en el repo oficial.

> Nota: en GitHub Free, el control se refuerza con **permisos + proceso**.

---

## 8) Configuración inicial (una sola vez) — Organización

### 8.1 Seguridad

- Activar **Require 2FA** para miembros y colaboradores.

### 8.2 Permisos base

- Configurar **Base permissions = None** (nadie tiene acceso por defecto).

### 8.3 Forks en repos privados

- Activar política de forking para repos privados:
  - Organization Settings → Forking policy → permitir forking en privados.
  - En cada repo: permitir/denegar forking según necesidad.
- En privados, el fork queda en la cuenta personal del desarrollador.

---

## 9) Roles y permisos (modelo mínimo)

Crear equipos:

- **TEAM-INTEGRADOR** → permiso **Write** en repo oficial.
- **TEAM-DEVS** → permiso **Triage** en repo oficial.

**Rotación del Integrador:**

- Se cambia semanalmente (ej. lunes).
- Integrador = único autorizado para: merges, tags, releases y despliegues.

---

## 10) Flujo diario (paso a paso) — con PR

1. Crear **Issue** en repo oficial (título claro + criterios de aceptación).
2. Hacer **fork** del repo oficial a la cuenta personal.
3. Crear rama en el fork:
   - `feature/<descripcion-corta>`
   - `fix/<descripcion-corta>`
   - `chore/<descripcion-corta>`
4. Commits pequeños y frecuentes (recomendado):
   - `feat: ...`
   - `fix: ...`
   - `chore: ...`
   - `docs: ...`
5. Abrir **PR** del fork hacia el repo oficial, incluyendo:
   - `Closes #<id>` (issue relacionado)
   - descripción y cómo probar
   - checklist
6. Revisión del otro desarrollador.
7. **Solo Integrador** hace merge y elimina la rama.
8. Issue queda cerrado (si se usó `Closes #id`).

---

## 11) Definition of Done (para aprobar un PR)

Un PR está listo para merge si:

- Está ligado a un Issue.
- Explica el cambio + pasos de prueba.
- No incluye secretos (tokens/llaves/contraseñas).
- Pasa CI (si aplica).
- Fue revisado por otra persona.
- No lo mergea el mismo autor.

---

## 12) Automatización mínima (GitHub Actions / CI)

### 12.1 Consideración de límite

- GitHub Free en organizaciones tiene un límite mensual de minutos de Actions (se debe controlar el consumo).

### 12.2 Workflows mínimos

- En PR: **lint + tests + build** (sin secretos).
- En main: **build + tests** (+ empaquetado si aplica).

---

## 13) Seguridad de dependencias (obligatorio)

Activar en cada repo:

- **Dependency graph**
- **Dependabot alerts**
- **Dependabot security updates**

Operación:

- Los PRs de Dependabot se revisan igual que cualquier PR.
- Solo el Integrador mergea.

---

## 14) Releases y despliegues

- Versionado con tags: `vX.Y.Z` (ej. `v1.4.0`)
- Solo el Integrador despliega.
- Cada despliegue se documenta en:
  - un Issue tipo “Deploy vX.Y.Z”, o
  - el Release.

---

## 15) Rutinas de mantenimiento

### Semanal (15 min)

- Cambiar Integrador (rotación).
- Revisar PRs abiertos y prioridades.
- Revisar Issues en curso.

### Mensual (30 min)

- Verificar 2FA y accesos.
- Revisar consumo de Actions y ajustar CI.
- Revisar alertas de Dependabot y tiempos de atención.

---

## 16) Plantillas listas para copiar

### 16.1 PR Template — `.github/pull_request_template.md`

```md
## Descripción

- Qué cambia:
- Motivo:

## Cómo probar

1.
2.
3.

## Checklist

- [ ] Issue relacionado (Closes #)
- [ ] Pruebas ejecutadas
- [ ] CI pasó (lint/tests/build)
- [ ] No incluye secretos

## Riesgo / reversa

- Riesgos:
- Cómo revertir:
```
