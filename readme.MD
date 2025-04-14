# Charla: Kritis y Grafeas  
**Evento:** Nerdear.la 2022  
**Ponente:** Juan Manuel Paniagua y Gaston DeSloover
**Tema:** Seguridad en la Cadena de Suministro de Software usando Kritis y Grafeas  

---

## Descripción

En esta charla se abordó la importancia de proteger la cadena de suministro de software. Se presentaron herramientas y frameworks de código abierto para garantizar la integridad de las imágenes de contenedores y artefactos de software en entornos Kubernetes. En particular, se explicó cómo **Kritis** y **Grafeas** pueden ser integrados en un pipeline de CI/CD para:
- Verificar vulnerabilidades.
- Aplicar políticas de seguridad.
- Emitir atestaciones que respalden el origen y la seguridad de las imágenes.

El enfoque se enmarca en el contexto de ataques de supply chain (como el caso de Solorigate y la vulnerabilidad LOG4J) y en cómo adoptar buenas prácticas para mitigar estos riesgos.

---

## Contenidos

### 1. Introducción a la Cadena de Suministro de Software
- **Problemas actuales:**  
  - Ataques en la cadena de suministro.
  - Vulnerabilidades en artefactos y contenedores.
- **Ejemplos mencionados:**  
  - Solorigate.
  - Vulnerabilidades LOG4J.

### 2. Framework SLSA (Supply-chain Levels for Software Artifacts)
- Descripción de SLSA como lista de verificación de estándares y controles para evitar la manipulación de artefactos.
- Niveles de implementación, desde la documentación hasta controles avanzados en la infraestructura.

### 3. Kritis: Protección para Kubernetes
- **¿Qué es Kritis?**  
  Una solución de código abierto que aplica políticas de seguridad en la implementación de contenedores en Kubernetes.
- **Funcionamiento:**  
  - Realiza escaneos de vulnerabilidades.
  - Consulta la API de metadatos de **Grafeas** para obtener información sobre la procedencia y vulnerabilidades de una imagen.
  - Aplica políticas de seguridad para permitir o denegar despliegues.
- **Modos operativos en Kritis:**
  - *check-and-sign:* Verifica el cumplimiento de la política y firma la imagen si es adecuada.
  - *check-only:* Solo verifica sin firmar.
  - *bypass-and-sign:* Crea una certificación omitiendo la verificación (para casos específicos).

### 4. Grafeas: La Fuente Central de Metadatos
- **¿Qué es Grafeas?**  
  Una API de metadatos de código abierto que permite almacenar, consultar y auditar información sobre artefactos de software.
- **Conceptos clave:**  
  - *Notas:* Descripciones de alto nivel de vulnerabilidades o propiedades.
  - *Ocurrencias:* Instanciaciones de notas que detallan cómo y cuándo aparece una vulnerabilidad o característica en un artefacto.
- **Importancia:**  
  Facilita la estandarización y automatización del análisis de seguridad en toda la cadena de suministro.

### 5. Integración de Kritis y Grafeas en el Pipeline de Desarrollo
- **Proceso:**  
  - Escaneo de la imagen.
  - Verificación de políticas.
  - Emisión de atestaciones.
  - Aplicación de controles (binary authorization).
- **Beneficios:**  
  - Mayor seguridad en los despliegues.
  - Automatización del cumplimiento de políticas.
  - Reducción del riesgo de vulnerabilidades en producción.

### 6. Casos de Uso y Ejemplos Prácticos
- Ejemplo de política para rechazar despliegues con vulnerabilidades críticas.
- Flujo de trabajo para generar certificaciones con **Kritis Signer**.
- Discusión sobre la importancia de auditar la procedencia y la integridad de las imágenes mediante herramientas de escaneo y análisis.

---

## Recursos y Enlaces de Interés

- [SLSA](https://slsa.dev/) – Framework para la seguridad de la cadena de suministro de software.
- [Kritis en GitHub](https://github.com/grafeas/kritis) – Repositorio de la solución Kritis.
- [Grafeas en GitHub](https://github.com/grafeas/grafeas) – Repositorio de la API de metadatos de software.
- [Kritis Signer Documentation](https://github.com/grafeas/kritis/blob/master/docs/signer.md) – Detalles sobre la herramienta para firmar imágenes.
- [Binary Authorization - Google Cloud](https://cloud.google.com/binary-authorization/docs/overview) – Seguridad en el despliegue de contenedores.
- [Atestación de Software](https://github.com/kelseyhightower/Grafeas/blob/master/case-studies/binary-authorization.md) – Caso de estudio sobre la validación de imágenes.

---

## Conclusión

La charla se centró en cómo utilizar herramientas de código abierto como Kritis y Grafeas para fortalecer la seguridad en la cadena de suministro de software, especialmente en entornos de Kubernetes. La integración de escaneo, verificación de políticas y emisión de atestaciones permite mitigar los riesgos asociados a vulnerabilidades en artefactos y contenedores, garantizando implementaciones seguras y confiables.
