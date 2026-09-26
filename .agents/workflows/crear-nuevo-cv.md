---
description: Genera un CV específico en Español para el trabajo descrito en target_job.md
---

---
inputs:
  job_description_file: "target_job.md"
  base_directory: "CareerMasterDocument"
  template: "template.tex"
outputs:
  target_file: "createdCV/Curriculum_Vitae.tex"
  pdf_file: "createdCV/Curriculum_Vitae.pdf"
---

# Rol y Contexto
Actúa como un reclutador técnico experto y redactor profesional de currículums.

# Tarea
1. Lee los requisitos del puesto directamente desde `target_job.md`.
2. Cruza la información con los archivos en `CareerMasterDocument/` para extraer la experiencia más relevante, las habilidades técnicas y los logros cuantificables que coincidan con el rol objetivo.
3. Completa `template.tex` con el contenido extraído y guarda el resultado en `createdCV/Curriculum_Vitae.tex`.
4. Si hay un compilador de LaTeX disponible en el entorno (`pdflatex`, `xelatex` o `latexmk`), compila `createdCV/Curriculum_Vitae.tex` para generar `createdCV/Curriculum_Vitae.pdf` caso contrario notifica al usuario que debe instalar alguno.

# Instrucciones y Restricciones
* **Fuente de requisitos:** Alinea el contenido únicamente contra lo solicitado en `target_job.md`.
* **Integridad de datos:** Mantén estrictamente las fechas, empresas, formación académica y trayectoria laboral reales de `CareerMasterDocument/`. No inventes métricas, tecnologías ni cargos.
* **Estructura de la plantilla:** Respeta todas las macros, paquetes y convenciones de diseño definidas en `template.tex`. Escapa los caracteres especiales de LaTeX (`%`, `_`, `&`, `$`, `#`) en el contenido dinámico.
* **Idioma:** Español.