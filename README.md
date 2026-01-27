<div align="center">

# 🚀 WONDERTECH SAS

### Repositorio Institucional & Estándares de Ingeniería

[![Status](https://img.shields.io/badge/Estado-Activo-success?style=for-the-badge&logo=github)](https://github.com/wondertech-sas)
[![Policies](https://img.shields.io/badge/Políticas-Estrictas-blue?style=for-the-badge&logo=shield)](PROT_001)
[![Odoo](https://img.shields.io/badge/Trazabilidad-Odoo-purple?style=for-the-badge&logo=odoo)](https://odoo.com)

<p align="center">
  <b>Bienvenido al ecosistema de desarrollo de Wondertech SAS.</b><br>
  Este repositorio es la regla principal para nuestros estándares de calidad, políticas de implementación y excelencia operativa.
</p>

</div>

---

## 🌟 Vision General

Este espacio no es solo un repositorio; es el **marco de gobierno** técnico para todos nuestros proyectos. Aquí definimos cómo construimos, probamos y entregamos software que impulsa nuestro negocio.

### 💎 Principios Fundamentales

| Principio                  | Descripción                                                              |
| :------------------------- | :----------------------------------------------------------------------- |
| **🛡️ Auditoría Total**     | Cada línea de código debe ser rastreable a un requerimiento de negocio.  |
| **🎯 ID de Odoo**          | El nexo sagrado entre la gestión y la ingeniería. Sin ID, no hay código. |
| **✅ Calidad vs Cantidad** | El código sin QA y documentación no existe.                              |

---

## 📜 Políticas de Implementación (OBLIGATORIO)

Para garantizar la integridad de nuestros sistemas, aplicamos las siguientes reglas inquebrantables a partir de la fecha de vigencia.

### 1. 🏷️ Estandarización de Nombres

Todo repositorio debe nacer con una identidad clara. El formato **estricto** es:

```bash
[ID_ODOO]_NOMBRE_DEL_PROYECTO_CON_GUION_BAJO
# Ejemplo: 1024_INTEGRACION_SERVIENTREGA
```

### 2. 📦 Reglas de Entrega (Definition of Done)

Una entrega **NO** será aceptada en producción a menos que cumpla con el **Estándar de Oro**:

- [ ] **Release Tag**: Versionado semántico estricto (`vX.Y.Z`).
- [ ] **Evidencia de QA**: Archivo obligatorio en `documentacion/QA.md`.
- [ ] **Notas de Entrega**: Descripción clara de cambios y valor aportado.

> ⚠️ **Advertencia**: _Si falta cualquiera de estos elementos, la entrega se considera **NULA**._

### 3. 📂 Estructura Sagrada del Repositorio

La organización es la base de la mantenibilidad. Tu repositorio **DEBE** respetar esta jerarquía:

```mermaid
graph TD
    A[📦 Root] --> B(📄 README.md)
    A --> C(📂 documentacion/)
    A --> D(📂 proyecto/)

    style A fill:#ff9900,stroke:#333,stroke-width:2px,color:white
    style B fill:#e1e1e1,stroke:#333,stroke-width:1px
    style C fill:#00b894,stroke:#333,stroke-width:2px,color:white
    style D fill:#0984e3,stroke:#333,stroke-width:2px,color:white
```

O en formato árbol simple:

```bash
/
├── 📄 README.md          # Tu punto de entrada y documentación
├── 📂 documentacion/     # Evidencia de QA y manuales
└── 📂 proyecto/          # Tu código fuente va aquí
```

---

## 🛠️ Flujos de Trabajo (Workflows)

Nuestra metodología se adapta a la complejidad del proyecto, asegurando siempre la calidad.

<details>
<summary><b>🔵 Flujo A: Desarrollo Ágil (Sin PR)</b></summary>
<br>

Ideal para proyectos individuales o fases iniciales.

1. **Dev** crea repo personal: `[ID]_PROYECTO`.
2. **QA/PM** validan funcionalidad.
3. **Dev** genera Release `v1.0.0` + Evidencia QA.
4. **Dev** transfiere la propiedad a la organización **Wondertech**.

</details>

<details>
<summary><b>🟣 Flujo B: Control Estricto (Con PR)</b></summary>
<br>

Para proyectos críticos y colaborativos.

1. **Fork** del repositorio oficial.
2. Desarrollo en ramas (`feature/`, `fix/`).
3. **Pull Request** hacia el repo oficial.
4. Revisión de código obligatoria.
5. Merge realizado **únicamente** por el Integrador asignado.

</details>

---

## 🚀 Stack & Herramientas

<div align="center">

|  Categoría  | Tecnologías                                                                                                                                                                                                         |
| :---------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|  **Core**   | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| **Gestión** | ![Odoo](https://img.shields.io/badge/Odoo-714B67?style=flat-square&logo=odoo&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white)                   |
| **DevOps**  | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)     |

</div>

---

<div align="center">
  <small>WONDERTECH SAS © 2026 — Construyendo el futuro con excelencia.</small>
</div>
