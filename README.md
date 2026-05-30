# github-actions-lab de Jose Antonio Perez Alias

<br>
<br>

---


## **0\. Configuración Inicial del Entorno**


Se inicializa el repositorio remoto bajo el nombre **github-actions-lab**. Acto seguido, se realiza el **commit** inicial que incluye este archivo **README.md** junto con el código fuente de la aplicación **hangman-front**.
<br>
<br>
## **¿Como Exportar el proyecto?** 

1. **Descarga en local:** Conseguimos las carpetas del proyecto original de Lemoncode (hangman-api, hangman-e2e y hangman-front) y las colocamos dentro de nuestro directorio de trabajo local github-actions-lab.
2. **Diagnóstico del estado (git status):** Consultamos a Git para ver qué archivos nuevos teníamos en nuestro ordenador que aún no existían en la nube (GitHub). Detectamos que:  
   * Teníamos las 3 carpetas nuevas sin rastrear (*untracked*).  
   * Teníamos un archivo README.md modificado localmente que **no** queríamos subir todavía porque queríamos redactarlo desde cero.  
2. **Envío a la nube (git push):** Subimos las carpetas a nuestro repositorio remoto de GitHub para que estén disponibles públicamente.
<br>
## **Comandos y Código Utilizado**

A continuación se detalla la secuencia exacta de comandos ejecutados en la terminal para completar el proceso con éxito:

### **1\. Comprobar el estado del repositorio**

Antes de hacer nada, comprobamos qué archivos estaban listos para ser procesados:
```
git status
```
<br>
![Captura](./capturas/tarea-1-1.png)
<br>

* **Resultado:** Git nos mostró en rojo las carpetas nuevas (hangman-\*) y el archivo README.md modificado.
<br>
<br>

### **2\. Preparar selectivamente solo los proyectos**

Para evitar subir el README.md que estamos modificando, preparamos únicamente las carpetas del juego usando sus rutas específicas separadas por un espacio:
```
git add hangman-api hangman-e2e hangman-front
```

### **3\. Crear el punto de guardado local**

Registramos estos cambios en el historial de versiones con un mensaje claro y descriptivo que explique qué estamos añadiendo:
```
git commit \-m "feat: añadir carpetas del proyecto hangman"
```
<br>
![Captura](./capturas/tarea-1-2.png)
<br>

### **4\. Subir los archivos a GitHub**

Finalmente, enviamos las carpetas confirmadas en el paso anterior a la rama principal (main) en el servidor remoto (origin):

```
git push origin main
```
<br>
![Captura](./capturas/tarea-1-3.png)
<br>
----

 <br>
## **1\. EJERCICIO 1: Diseño del Workflow de CI (Frontend)**

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

<br>
<br>

---




