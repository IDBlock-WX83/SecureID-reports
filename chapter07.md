# Capítulo VII: Product Implementation, Validation & Deployment
---

## 7.1. Software Configuration Management
### 7.1.1. Software Development Environment Configuration
---
Este segmento describe los programas de software esenciales para facilitar la colaboración en el ciclo de vida de los productos digitales dentro del proyecto. Se mencionan los nombres de los programas, su función en el proyecto, y los enlaces o rutas de descarga correspondientes para su acceso.

**Visual Studio Code**

> Este entorno de desarrollo se empleará para crear tanto la landing page como la aplicación móvil. Flutter será utilizado para el desarrollo de la parte móvil.

Link: https://code.visualstudio.com/download

**Github**

> Esta herramienta se empleará para administrar el control de versiones en todos nuestros repositorios.

Link: https://github.com/

**Figma**

> Esta plataforma se utiliza para diseñar los prototipos de nuestra aplicación móvil.

Link: https://www.figma.com/

**Firebase App Distribution**

> Esta herramienta facilita la distribución de versiones de aplicaciones móviles.

Link: https://firebase.google.com/docs/app-distribution?hl=es

**Railway**

> Se utilizará para realizar el despliegue del servicio backend.

Link: https://railway.app/

**Miro**

> Se emplea para llevar a cabo sesiones de brainstorming y para partes específicas del informe, como el análisis del escenario actual y el escenario futuro deseado.

Link: https://miro.com/es/

**Uxpressia**

> Se utiliza para ilustrar las secciones relacionadas con el Needfinding.

Link: https://uxpressia.com/

**Lucidchart**

> Se emplea para la elaboración de diagramas de clases y diagramas de bases de datos.

Link: https://www.lucidchart.com/pages

**Visual Paradigm**

> Se utiliza para diseñar la arquitectura de software de nuestro proyecto.

Link: https://www.visual-paradigm.com/

### 7.1.2. Source Code Management
---
**Landing Page**

![](./assets/7.1.2.SourceCodeManagement/landingPage.png)

Link: https://github.com/IDBlock-WX83/landing-page

----

**Convenciones de GitHub**

> The main branch:

El modelo de desarrollo se fundamenta en prácticas bien definidas. El repositorio central cuenta con dos ramas principales de duración indefinida:

*   master: Esta rama, conocida por todos los usuarios de Git, representa un estado listo para producción.
*   develop: En paralelo a master, la rama develop contiene los últimos cambios en desarrollo para la próxima versión. Funciona como la rama de integración y es donde se generan las compilaciones automáticas diarias.

Una vez que el código en la rama develop se estabiliza y está listo para ser lanzado, todos los cambios se fusionan en master y se etiquetan con un número de versión. De este modo, cada fusión en master marca un nuevo lanzamiento de producción, lo que facilita la automatización del despliegue de software.

![](./assets/7.1.2.SourceCodeManagement/mainBranches.png)

> Feature branches:

Bifurcadas desde: develop
Fusionadas de nuevo en: develop
Convención de nombres: Cualquier nombre, excepto master, develop, release-, o hotfix-

Las ramas de características, también llamadas ramas de temas, se utilizan para desarrollar nuevas funcionalidades, ya sea para lanzamientos cercanos o futuros. Estas ramas se mantienen activas hasta que la nueva funcionalidad esté lista para integrarse en la rama develop o se descarta si resulta no ser adecuada.

![](./assets/7.1.2.SourceCodeManagement/featuresBranches.png)

### 7.1.3. Source Code Style Guide & Conventions
---

Como convención general, todo el código realizado por los miembros del equipo debe redactarse en
completo inglés.

**HTML**

Use Lowercase Element Names: Se recomienda usar lowercase para los nombres de los elementos HTML.

Close All HTML Elements: Se recomienda cerrar todos los elementos HTML.

Use Lowercase Attribute Names: Se recomienda usar lowercase para los nombres de los atributos HTML.

Always Specify alt, width, and height for Images: Se recomienda seguir estas convenciones en caso de que la imagen no se puede mostrar y ayudar con la accesibilidad del contenido.

Spaces and Equal Signs: Se recomienda no usar espacios en blanco entre las entidades para una mejor lectura.

Para más información sobre las convenciones de HTML se usará como referencia:
https://www.w3schools.com/html/html5_syntax.asp

**CSS**

ID and Class Naming: Usar nombres de clases e ID significativos que expresen el propósito del elemento.

ID and Class Name Style: Usar nombres cortos para nombrar ID o clases, pero lo suficientemente largo para saber cuál es su
propósito.

Shorthand Properties: Usar CSS shothand properties tanto como sea posible para que el código sea más eficiente y entendible.

ID and Class Name Delimiters: Separar las palabras en ID y clases con un guión.

Selector and Declaration Separation: Separar los selectores y declaraciones en nuevas líneas.

Para más información sobre las convenciones de CSS se usará como referencia:
https://google.github.io/styleguide/htmlcssguide.html#CSS

**JavaScript**

Use expanded syntax: Cada línea de JavaScript en una nueva línea, con la llave de apertura en la misma línea de su
declaración y la llave de cierre en una nueva línea al final.

Variable naming: Para el nombre de las variables usar lowerCamelCase.

Declaring variables: Para la declaración de variables usar las palabras reservadas let y const, no usar var.

Use strict equality: Siempre usar la igualdad o inigualdad estricta.

Function naming: Para el nombre de las funciones usar lowerCamelCase.

Para más información sobre las convenciones de JavaScript se usará como referencia:
https://www.w3schools.com/js/js_conventions.asp

**TypeScript**

Camel case: Usar camelCase cuando nombramos variables y funciones. También se debe usar camelCase en los miembros de una clase y sus métodos. En la interface, el camelCase se usa para nombrar miembros.

Pascal case: Usar pascal case para nombres de clases. En la interface, sirve para nombres.

Para más información sobre las convenciones de TypeScript se usará como referencia:
https://basarat.gitbook.io/typescript/styleguide#array

**Gherkin**

Discernible Given-When-Then Blocks: Se recomienda aplicar sangría a los bloques, para saber cuándo iniciar y terminan.

![](./assets/7.1.3.SourceCodeStyleGuide&Conventions/DiscernibleGivenWhenThenBlocks.png)

Steps with Tables: Si necesitamos entrada de una tabla en nuestros pasos, para que sea reconocible, añadiremos dos puntos al final del paso.

![](./assets/7.1.3.SourceCodeStyleGuide&Conventions/StepswithTables.png)

Reducing Noise: Se recomienda usar valores predeterminados para campos que requiere el software pero que no son relevantes para el escenario.

![](./assets/7.1.3.SourceCodeStyleGuide&Conventions/ReducingNoise.png)
 
Parameters in Steps: Para el ejemplo anterior, se pudo notar la inclusión de comillas simples para los parámetros en un paso, lo cual facilita la detección de estos.

Newlines within Scenarios: En caso de que el escenario se está alargando, es recomendable agregar nuevas líneas entre cada paso para que los bloques sean más legibles.

![](./assets/7.1.3.SourceCodeStyleGuide&Conventions/NewlineswithinScenarios.png)
 
Newlines between scenarios and separator comments: Cuando se tienen muchos escenarios, se vuelve difícil saber el punto donde inicia o termina otro. Por ello, se recomiendo agregar una línea de separación entre escenario y un separador de comentarios.

![](./assets/7.1.3.SourceCodeStyleGuide&Conventions/Newlinesbetweenscenariosandseparatorcomments.png)

### 7.1.4. Software Deployment Configuration.
---
Esta sección describe la configuración requerida para realizar correctamente el despliegue de cada uno de los productos digitales en la solución, utilizando las herramientas específicas para cada caso.

**Despliegue de la Landing Page**

Para el despliegue de la Landing Page, se utilizará la plataforma Netlify. A continuación, se detallan los pasos necesarios:

- Configuración del Repositorio: El código fuente de la Landing Page y la Aplicación Web se almacenará en un repositorio en la plataforma Github.
- Creación del Sitio en Netlify: Se creará un nuevo sitio en Netlify vinculado al repositorio que contiene el código fuente de la Landing Page y la Aplicación Web.
- Configuración de Build y Deploy: Netlify proporciona una integración continua (CI/CD) automatizada.
- Configuración de Dominio Personalizado: Opcionalmente, se puede configurar un dominio personalizado para el sitio web desplegado en Netlify.

**Despliegue de la Aplicació Móvil en Firebase App Distribution**

Para el despliegue de la aplicación en Firebase App Distribution, se seguirán los siguientes pasos:

-   Configuración del Repositorio: El código fuente de la aplicación se almacenará en un repositorio en GitHub, asegurando que esté actualizado con la última versión lista para pruebas.
-   Integración con Firebase: Conectar Firebase App Distribution al proyecto de la aplicación móvil, permitiendo la distribución de las versiones beta a los testers.
-   Configuración de Build y Deploy: Configurar una pipeline de integración continua (CI/CD) con herramientas como Fastlane o GitHub Actions para automatizar la creación de nuevas versiones y su despliegue en Firebase App Distribution.
-   Distribución de la Aplicación: Subir la APK o IPA directamente a Firebase App Distribution, donde los testers seleccionados recibirán una notificación con acceso a la nueva versión.
-   Gestión de Testers: Gestionar los testers desde Firebase, añadiéndolos o eliminándolos según sea necesario, para asegurar que las personas correctas tengan acceso a las versiones.

**Despliegue del Web Service**

Para el despliegue del Web Service, se utilizará la plataforma Railway. A continuación, se detallan los pasos necesarios:

- Configuración del Repositorio: El código fuente del Web Service se almacenará en un repositorio en la plataforma Github.
- Creación del Proyecto en Railway: Se creará un nuevo proyecto en Railway vinculado al repositorio que contiene el código fuente del Web Service.
- Configuración de Variables de Entorno: Railway permite configurar fácilmente variables de entorno para el proyecto. Se configurarán las variables de entorno necesarias, como credenciales de base de datos u otras configuraciones específicas del entorno.
- Despliegue Automatizado: Una vez configurado el proyecto en Railway, se puede habilitar el despliegue automático para que el servicio se actualice automáticamente cada vez que se realicen cambios en el repositorio.
- Monitoreo y Escalado: Railway proporciona herramientas para monitorear el rendimiento del servicio y escalarlo según sea necesario, asegurando un funcionamiento óptimo en todo momento.

## 7.2. Solution Implementation
### 7.2.1. Sprint 1
#### 7.2.1.1. Sprint Planning 1
---

#### 7.2.1.2. Sprint Backlog 1
---

#### 7.2.1.3. Development Evidence for Sprint Review
---

#### 7.2.1.4. Testing Suite Evidence for Sprint Review
---

#### 7.2.1.5. Execution Evidence for Sprint Review
---

#### 7.2.1.6. Services Documentation Evidence for Sprint Review
---

#### 7.2.1.7. Software Deployment Evidence for Sprint Review
---

#### 7.2.1.8. Team Collaboration Insights during Sprint
---