# github-actions-lab de Jose Antonio Perez Alias



## **0\. Configuración Inicial del Entorno**

Se inicializa el repositorio remoto bajo el nombre **github-actions-lab**. Acto seguido, se realiza el **commit** inicial que incluye este archivo **README.md** junto con el código fuente de la aplicación **hangman-front**.

## **1\. Diseño del Workflow de CI (Frontend)**

Para el desarrollo del pipeline de integración continua, se crea la rama de trabajo **add-ci-workflow**. El objetivo es implementar un flujo automatizado que valide el código bajo las siguientes condiciones:

### **Disparadores (Triggers)**

El **workflow** se ejecutará de forma automática únicamente cuando se cumplan simultáneamente estos dos requisitos:

1. Se detecten modificaciones en el proyecto **hangman-front**.  
2. Se abra o actualice una **pull request**.

### **Etapas del Pipeline (Jobs)**

* **Build:** Compilación del proyecto para verificar que no existan errores sintácticos o de dependencias.  
* **Unit Tests:** Ejecución de la suite de pruebas unitarias para garantizar la estabilidad del código.

### **Estructura de Archivos**

En GitHub Actions, los flujos de trabajo deben residir en el directorio específico **.github/workflows/** ubicado en la raíz del repositorio.  
Para este primer pipeline de CI, se define el archivo de configuración en formato YAML bajo el nombre **ci.yaml**, quedando la estructura de directorios de la siguiente manera:

## **Anatomía de ci.yaml**

* **Atributo name:** Se define la propiedad fundamental para identificar el flujo en la interfaz de GitHub. Para este caso, lo nombramos como **Integración continua**.

### **💡 Un tip pro de CI/CD para tu archivo YAML:**

Cuando configures el trigger por paths para que solo actúe en el frontend, asegúrate de estructurarlo así en tu ci.yaml para que cumpla estrictamente lo que pides:

YAML  
on:  
  pull\_request:  
    paths:  
      \- 'hangman-front/\*\*'

Esto evitará que el pipeline se dispare innecesariamente si cambias cosas en la raíz o en otros proyectos del repo. ¿Quieres que te ayude a redactar el código YAML completo para este flujo?

