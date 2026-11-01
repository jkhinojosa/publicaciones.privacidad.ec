---
title: 'Lanzamiento del LMS Titular: Educación y Evangelización en Privacidad para Organizaciones'
date: '2026-05-26 10:00'
taxonomy:
    category: [blog, releases]
    tag: [lms-titular, semver, v2.1.0, privacidad, firmaec, spdp]
summary: 'Esta iteración presenta la creación y despliegue del LMS Titular (Academia Ciudadana) en la ruta /lms-titular. Diseñamos un servicio educativo altamente gamificado (XP, rachas, energía de corazones) y estructurado en 3 niveles para capacitar a colaboradores y ciudadanos sobre derechos ARCO+, reclamaciones directas al DPO y escalamiento ante la Superintendencia (SPDP) mediante FirmaEC.'
---

Esta iteración presenta la creación y despliegue del **LMS Titular (Academia Ciudadana)** en la ruta `/lms-titular`. Diseñamos un servicio educativo altamente gamificado (XP, rachas, energía de corazones) y estructurado en 3 niveles (cada 4 meses) para capacitar a los colaboradores y ciudadanos sobre sus derechos ARCO+, reclamaciones directas al DPO y escalamiento ante la Superintendencia (SPDP) mediante FirmaEC.

===

### [Nueva Función] Ecosistema Educativo LMS Titular
* **LMS Titular:** Servidor independiente montado en el puerto `3002` con tecnología React + Vite y Vanilla CSS, mobile-first y premium.
* **Ruta de aprendizaje modular:** Dividida en tres niveles de 4 meses:
  1. **Nivel 1:** Tus Datos, Tus Derechos.
  2. **Nivel 2:** Contacto y Reclamo Directo al DPO (15 días de respuesta).
  3. **Nivel 3:** Denuncia Administrativa ante la SPDP, FirmaEC y ciberseguridad práctica.

### [Nueva Función] Recursos de Microlearning e Interacción
* **Multimedia:** Reproductor de Video interactivo simulado y Reproductor de Audio (Podcast) con guiones de storytelling elaborados por el Guardián-EducaDatos.
* **Infografías interactivas:** Diagramas SVG/CSS que representan los flujos de escalamiento y plazos legales.
* **Evaluación gamificada:** Quizzes integrados con 3 preguntas tipo Bloom (Comprensión, Aplicación, Riesgo) y lógica de pérdida de corazones de energía.

### [Nueva Función] Mesa de Asesores PDP & Simulador
* **Simulador de Reclamaciones integrado:** Los usuarios redactan formalmente sus cartas de derechos y el sistema audita si cumplen los requisitos (copia de cédula, FirmaEC para SPDP, reclamo previo).
* **AdvisorsPanel dinámico:** Retroalimentación constante en vivo de Guardián-EducaDatos (Evangelizador), Tutor-PDP (Legal Compliance) y Pedagogo-PDP (Andragogía).

---

> [!NOTE]
> **Clasificación SemVer:** Esta iteración se clasifica como **v2.1.0 (Menor)** al enriquecer el ecosistema de privacidad.ec con una nueva aplicación educativa dirigida a los titulares sin alterar la compatibilidad ni los endpoints del GRC o el LMS de DPOs existente.
