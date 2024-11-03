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

- Configuración del Repositorio: El código fuente de la Landing Page se almacenará en un repositorio en la plataforma Github.
- Creación del Sitio en Netlify: Se creará un nuevo sitio en Netlify vinculado al repositorio que contiene el código fuente de la Landing Page.
- Configuración de Build y Deploy: Netlify proporciona una integración continua (CI/CD) automatizada.
- Configuración de Dominio Personalizado: Opcionalmente, se puede configurar un dominio personalizado para la landing page desplegado en Netlify.

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
| Sprint#        | Sprint 1                      |
|----------------|-------------------------------|
| **Sprint Planning Background** |   |
| Date           | 01/11/2024                    |
| Time           | 11:00 pm                      |
| Location       | Google meet                   |
| Prepared By    | Aldo Pastrana |
| Attendees (to planning meeting) | Aldo Pastrana / Anderson Ore / Max Sabino / Sebastian Hernandez / Rodrigo López |
| **Sprint n-1 Review Summary** | Este es el primer sprint, no hay reviews anteriores. |
| **Sprint n-1 Retrospective Summary** | El equipo usará HTML, CSS y JavaScript para el desarrollo del Landing Page y Flutter para el desarrollo de la Aplicación Móvil |
| **Sprint Goal & User Stories** |   |
| Sprint n Goal  | Realizar el desarrollo del Landing Page y Aplicación Móvil |
| Sprint n Velocity | 14 |
| Sum of story Points | 63 |

#### 7.2.1.2. Sprint Backlog 1
---
<table>
    <tr>
        <th colspan="1">Sprint #</th>
        <th colspan="5">Sprint n</th>
    </tr>
    <tr>
     <th colspan="2">User Story</th>
        <th colspan="6">Work-Item / Task</th>
    </tr>
    <tr>
        <td>Id</td>
        <td>Title</td>
        <td>Id</td>
        <td>Title</td>
        <td>Description</td>
        <td>Estimation (Hours)</td>
        <td>Assigned To</td>
        <td>Status (To-do / In-Process / To-Review Done)</td>
    </tr>
    <tr>
        <td>US17</td>
        <td>Visualización de la Propuesta de Valor</td>
        <td>TK01</td>
        <td>Visualización de la Propuesta de Valor</td>
        <td>Como visitante de la landing page, quiero entender rápidamente la propuesta de valor de
SecureID para saber cómo esta plataforma puede ayudarme a obtener una identificación
digital segura.</td>
        <td>1</td>
        <td>Aldo Pastrana</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US18</td>
        <td>Información sobre los Beneficios de SecureID</td>
        <td>TK01</td>
        <td>Información sobre los Beneficios de SecureID</td>
        <td>Como residente de una zona rural, quiero conocer los beneficios de usar SecureID para
entender cómo puede mejorar mi acceso a servicios esenciales.</td>
        <td>1</td>
        <td>Anderson Ore</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US19</td>
        <td>Información sobre Integración con Sistemas Gubernamentales</td>
        <td>TK01</td>
        <td>Información sobre Integración con Sistemas Gubernamentales</td>
        <td>Como autoridad local, quiero ver información sobre cómo SecureID se integra con los
sistemas gubernamentales para asegurarme de que puede ser implementado fácilmente
en mi comunidad.</td>
        <td>1</td>
        <td>Max Sabino</td>
        <td>Donei</td>
    </tr>
    <tr>
        <td>US20</td>
        <td>Acceso a Recursos Educativos</td>
        <td>TK01</td>
        <td>Acceso a Recursos Educativos</td>
        <td>Como residente de una zona rural, quiero acceder a recursos educativos en la plataforma
SecureID para aprender a utilizarla de manera efectiva.</td>
        <td>1</td>
        <td>Sebastian Hernandez</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US21</td>
        <td>Llamado a la Acción para Registro</td>
        <td>TK01</td>
        <td>Llamado a la Acción para Registro</td>
        <td>Como visitante de la landing page, quiero ver un claro llamado a la acción para
registrarme en SecureID y comenzar a utilizar la plataforma.</td>
        <td>1</td>
        <td>Rodrigo López</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US22</td>
        <td>Optimización para Dispositivos Móviles</td>
        <td>TK01</td>
        <td>Optimización para Dispositivos Móviles</td>
        <td>Como visitante de la landing page, quiero que la página esté optimizada para dispositivos
móviles para poder navegarla cómodamente desde mi teléfono o tableta.</td>
        <td>1</td>
        <td>Aldo Pastrana</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US01</td>
        <td>Registro de Identificación Digital</td>
        <td>TK01</td>
        <td>Registro de Identificación Digital</td>
        <td>Como residente de la zona rural, quiero registrar mi identificación digital en la plataforma
SecureID para acceder a servicios esenciales como salud, educación y asistencia social.</td>
        <td>1</td>
        <td>Anderson Ore</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US02</td>
        <td>Verificación de Identidad</td>
        <td>TK01</td>
        <td>Verificación de Identidad</td>
        <td>Como autoridad local, quiero verificar la identidad digital de los residentes a través de la
plataforma SecureID para asegurarme de que pueden acceder a los recursos y servicios sin
fraude.</td>
        <td>2</td>
        <td>Max Sabino</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US03</td>
        <td>Acceso a Servicios Esenciales</td>
        <td>TK01</td>
        <td>Acceso a Servicios Esenciales</td>
        <td>Como residente de la zona rural, quiero acceder a servicios como salud, educación y
asistencia social a través de la plataforma SecureID utilizando mi identificación digital.</td>
        <td>2</td>
        <td>Sebastian Hernandez</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US06</td>
        <td>Integración con Servicios Gubernamentales</td>
        <td>TK01</td>
        <td>Integración con Servicios Gubernamentales</td>
        <td>Como autoridad local, quiero que la plataforma SecureID esté integrada con los sistemas
gubernamentales existentes para que pueda gestionar y verificar identidades de manera
más eficiente.</td>
        <td>2</td>
        <td>Rodrigo López</td>
        <td>Done</td>
    </tr>
    <tr>
        <td>US07</td>
        <td>Interfaz de Usuario Accesible</td>
        <td>TK01</td>
        <td>Interfaz de Usuario Accesible</td>
        <td>Como residente de la zona rural con bajo nivel de alfabetización digital, quiero una interfaz
de usuario que sea simple y fácil de usar para que pueda gestionar mi identificación digital
sin dificultad.</td>
        <td>1</td>
        <td>Aldo Pastrana</td>
        <td>Done</td>
    </tr>
</table>

#### 7.2.1.3. Development Evidence for Sprint Review
---
| Repository          | Branch            | Commit Id | Commit Message           | Commit Message Body                                  | Committed on (Date) |
|---------------------|-------------------|-----------|--------------------------|------------------------------------------------------|---------------------|
| https://github.com/IDBlock-WX83/landing-page | main | 25c01e5d268b9ab220ac25770029a360b5cb652b  | update title | update title | 01/11/2024         |
| https://github.com/IDBlock-WX83/landing-page | main | 642bf896b8b44947bd7334d5fa9dd19cbe4f7974  | Update index.html | Update index.html | 01/11/2024         |
| https://github.com/IDBlock-WX83/landing-page | main | 92c68a7af8d002b08451fb86e6ef95d1dfa68a97  | Update index.html | Update index.html | 01/11/2024         |
| https://github.com/IDBlock-WX83/landing-page | main | d0f5a95cb84613b5f52d7076dfc2eb81af0c4586  | first commit | first commit | 25/09/2024         |
| https://github.com/IDBlock-WX83/landing-page | main | 0da8bbea46cc7d52a1f870e15a67cd9488566f9c  | añadiendo vistas de colaboradores y beneficios | añadiendo vistas de colaboradores y beneficios | 01/11/2024         |
| https://github.com/IDBlock-WX83/SecureID-mobile-application | main | c664f66ba8709e37173b7c4815c79c0f8381fedd  | Add welcome_screen | Add welcome_screen | 22/11/2024         |
| https://github.com/IDBlock-WX83/SecureID-mobile-application | main | 3e6681c73d24c6959570e3c29623c67800025d1b  | add face capture screen | add face capture screen | 31/05/2024         |
| https://github.com/IDBlock-WX83/SecureID-mobile-application | main | eed56013a1ccda123ad44400dcbed51ec075256c  | Adding service management | Adding service management | 01/11/2024         |
| https://github.com/IDBlock-WX83/SecureID-mobile-application | main | ad62519d59894302bbce65af1afa8749348f4e56  | Update menu screen. Routing to services | Update menu screen. Routing to services | 01/11/2024         |
| https://github.com/IDBlock-WX83/SecureID-mobile-application | main | 247f4d39e0994f1c6cd8ffc624fd52de5a346ea6  | update data user | update data user | 01/11/2024         |

#### 7.2.1.4. Testing Suite Evidence for Sprint Review
---
Para esta entrega no se ha presentado un backend funcional, se presento un fake API, por lo que los unit tests, integration tests y acceptance tests automaizados, para
web services relacionados con los user stories no realizara en esta entrega.

#### 7.2.1.5. Execution Evidence for Sprint Review
---
> Se realizó el landing page enfocado a nuestra propuesta como startup, evidenciando nuestro compromiso como equipo. 
Las tareas a realizar en cada sprint para la elaboración del landing page fueron:
- Planteamiento y desarrollo sobre nuestros componentes de estrategia empresarial como lo que es la presentacion de las ofertas y ventajas del servicio de SecureID.
-  Ofrecemos una descripción general del servicio, luego detallamos las características específicas del producto, y finalmente presentamos testimonios y un formulario de contacto.
- Presentamos información en secciones bien definidas lo cual facilita la navegación del usuario por áreas de interés específicas.

![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/landingpage.png)

> Asimismo, se realizo la aplicación móvil enfocado en el usuario final para ofrecerle un servicio eficaz y de calidad. Ademas, se realizaron tareas en el sprint para la elaboración de la aplicación móvil. A continuación, se muestran algunas de las interfaces mas importantes desarrolladas.

- La interfaz "Menu" de los usuarios residentes rurales donde podran visualizar las funcionalilades que tiene la aplicación móvil

    ![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/menuresidentes.png)

- La interfaz "Documento de Identidad" de los usuarios residentes rurales donde podran visualizar su  documentación digital

    ![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/identificacion.png)

- La interfaz "Servicios" de los usuarios residentes rurales podran visualizar los diversos servicios esenciales

    ![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/servicios.png)

- La interfaz "Menu" de los usuarios autoridades locales donde podran visualizar las funcionalilades que tiene la aplicación móvil

    ![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/menuautoridades.png)

- La interfaz "Buscar Residente" de los usuarios autoridades locales donde podran visualizar y buscar a los residents registrados

    ![](./assets/7.2.1.5.ExecutionEvidenceforSprintReview/buscarresidente.png)

#### 7.2.1.6. Services Documentation Evidence for Sprint Review
---
La landing page y aplicación móvil de nuestro proyecto se desarrollaron utilizando el sistema de control de versiones de Git, lo cual se puede verificar en el repositorio correspondiente del proyecto respectivamente: https://github.com/IDBlock-WX83/landing-page https://github.com/IDBlock-WX83/SecureID-mobile-application 

- Por otro lado, utilizamos HTML, CSS, JavaScript para realizar la página de nuestro landing page.

![](./assets/7.2.1.6.ServicesDocumentationEvidenceforSprintReview/landingpage.png)

- Asimismo, utilizamos Flutter para realizar las interfaces de nuestra aplicación móvil.

![](./assets/7.2.1.6.ServicesDocumentationEvidenceforSprintReview/mobile.png)

#### 7.2.1.7. Software Deployment Evidence for Sprint Review
---
En este Sprint, se ha completado el despliegue de la landing page. Esto ha implicado la creación de cuentas, la configuración de recursos en proveedores de nube y la configuración de proyectos de desarrollo para la integración.

Hemos seguido los mismos pasos para los dos despliegues.

1. Crear una cuenta en Netlify:
Acceder a https://www.netlify.com/ y nos creamos una cuenta

<img src="./assets/7.2.1.7.SoftwareDeploymentEvidenceforSprintReview/netlifylogin.png" width="700"/>|

2. Conectar Netlify con el repositorio:
En Netlify, hacer clic en "New site".
Seleccionar "Import from Git".
Conectar la cuenta de GitHub.
Seleccionamos el repositorio que contiene nuestra landing page.
Hacer clic en "Deploy site".

<img src="./assets/7.2.1.7.SoftwareDeploymentEvidenceforSprintReview/netlifyconectar.png" width="700"/>|

3. Configurar la landing page:
Netlify te asignará una URL temporal a nuestra landing page.

<img src="./assets/7.2.1.7.SoftwareDeploymentEvidenceforSprintReview/netlifydeploy.png" width="700"/>|

4. Desplegar la landing page:
Cuando hemos realizado todos los cambios necesarios, hacer clic en "Deploy".

<img src="./assets/7.2.1.7.SoftwareDeploymentEvidenceforSprintReview/netlifydeployoficial.png" width="700"/>|

#### 7.2.1.8. Team Collaboration Insights during Sprint
---

**Landing Page**

> Hemos desarrollado la implementacion de la Landing Page en ramas de la siguiente manera

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/ramaslanding.png" width="700"/>

> Commits hechos

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/commitslanding.png" width="700"/>

> Collaboration

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/collaborationlanding.png" width="700"/>

**Mobile Application**

> Hemos desarrollado la implementacion de la Mobile App en ramas de la siguiente manera

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/ramasgithub.png" width="700"/>

> Commits hechos

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/commitsgithub.png" width="700"/>

> Collaboration

<img src="./assets/7.2.1.8.TeamCollaborationInsightsduringSprint/collaboration.png" width="700"/>

## 7.3. Validation Interviews
---

### 7.3.1. Diseño de Entrevistas

**Objetivo de la Entrevista**

Evaluar la efectividad, usabilidad y percepción de seguridad de SecureID en su landing page, aplicación móvil, centrándonos en las principales funcionalidade y la percepción del usuario sobre la tecnología blockchain aplicada a la identificación digital.

> Elementos a Incluir en la Sesión de Validación para el segmento objetivo “Residentes”.

1. Landing Page de SecureID

-   Presentación del Landing Page:

    Pregunta: ¿Cómo describirías la forma en que se presenta la información en la página de inicio?

-   Navegación y Usabilidad:
    
    Pregunta: ¿Encuentras que la navegación del sitio es intuitiva y fácil de entender?

-   Valor Propuesto:
    
    Pregunta: ¿Entiendes claramente cuál es el valor de SecureID al ver la página de inicio?

-   Captación de Datos:
    
    Pregunta: ¿Consideras que la página captura de manera efectiva la información necesaria de los usuarios?

2. Aplicación Móvil de SecureID

-   Generar Identificación Virtual (Funcionalidad Clave):
    
    Pregunta: ¿Es fácil entender el proceso para crear tu identificación virtual? ¿Te sientes seguro?

-   Interacción y Diseño de la Aplicación:
    
    Pregunta: ¿Encuentras que el diseño y la forma en que interactúas con la aplicación son intuitivos?

-   Feedback del Usuario sobre Funcionalidades de Blockchain:
   
    Pregunta: ¿Qué piensas sobre que la app use blockchain para proteger tus datos? ¿Te da más confianza o te genera dudas?

-   Consultar Historial de Transacciones:
    
    Pregunta: ¿Te resulta útil poder ver un historial de actualizaciones y cambios?

-   Accesibilidad y Facilidad de Navegación:

    Pregunta: ¿Encuentras fácil acceder a la información de cada servicio? ¿Los íconos o botones son intuitivos?

-   Interacción con los Servicios:

    Pregunta: ¿Te gustaría que esta sección permita alguna interacción adicional, como consultas o solicitud de servicios específicos?

> Elementos a Incluir en la Sesión de Validación para el Segmento Objetivo "Autoridades Locales"

1. Landing Page de SecureID

-   Presentación del Landing Page:
    
    ¿Cómo describirías la forma en que se presenta la información y el acceso administrativo en la página de inicio?

-   Navegación y Usabilidad:
    
    ¿Encuentras que la navegación del sitio es intuitiva y fácil de entender desde una perspectiva administrativa?

-   Valor Propuesto para la Administración:

    ¿Percibes claramente cuál es el valor de SecureID para facilitar la administración de servicios?

-   Captación y Visualización de Datos:

    ¿Consideras que la página captura y visualiza de manera efectiva la información necesaria de los residentes para fines administrativos?

2. Aplicación Móvil de SecureID para la Administración de Identificaciones y Servicios

-   Gestión de Identificaciones Virtuales (Funcionalidad Clave):
    
    ¿Es fácil para ti comprender y utilizar el proceso de generación y administración de identificaciones virtuales de los residentes?

-   Interacción y Diseño de la Aplicación para Autoridades:

    ¿Encuentras que el diseño y la forma en que interactúas con las opciones administrativas son intuitivos?

-   Feedback sobre las Funcionalidades de Blockchain para la Seguridad de los Datos:

    ¿Qué piensas sobre el uso de blockchain para asegurar los datos de los residentes? ¿Crees que mejora la seguridad de la información que gestionas?

-   Consultar Historial de Transacciones y Cambios (Seguimiento Administrativo):

    ¿Te resulta útil tener acceso al historial de transacciones y cambios en los perfiles de los residentes?

3. Gestión de Servicios Brindados a los Residentes

-   Accesibilidad y Facilidad para Administrar la Información de los Servicios:
    
    ¿Encuentras sencillo acceder y actualizar la información de cada servicio (salud, educación, agua potable, energía)?

-   Interacción para Consultas o Solicitudes de Servicios por Parte de los Residentes:

    ¿Te gustaría que esta sección permita una mayor interacción con los residentes, como recibir y gestionar consultas o solicitudes específicas?

### 7.3.2. Registro de Entrevistas
---

# Entrevista a Carlos De La Cruz Villarreal - Residentes Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/carlos.png)

**Resumen de Entrevista:**

Carlos De La Cruz Villarreal, a interactuar con la landing page nos indica que percibe la información correctamente. Asimismo, nos comenta que la navegación es fácil e intuitivo para los usuarios y comprende claramente el valor de SecureID. Ademas, nos dice que captura de manera efectiva la atención de los usuarios. Luego pasando a la aplicación móvil, nos comenta que el proceso para crear una identificación virtual es fácil, seguro e intuitivo. Tambien, nos dice que al utilizar blockchain le da confianza para la protección de sus datos. Finalmente, le es fácil acceder a la información de cada servicio que brinda la aplicación móvil. 

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 00:00 - 06:44

---

# Entrevista a Isaac - Residentes Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/isaac.png)

**Resumen de Entrevista:**

Isaac nos dice que que la landing page de la plataforma incluye secciones claras como Sobre Nosotros, Entrevistas, Experiencia de Usuarios y un formulario de contacto, con navegación intuitiva y opciones de idioma. En la aplicación móvil, el registro requiere datos completos del usuario y permite la subida del DNI, con un proceso fácil de entender según el entrevistado. La app es intuitiva, fácil de usar y emplea blockchain para proteger los datos, generando confianza. El documento de identidad digital muestra información relevante, y la aplicación facilita el acceso a servicios sociales como salud, educación y agua, con una interfaz intuitiva y completa sin necesidad de funcionalidades adicionales.

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 06:45 - 11:29

---

# Entrevista a Wendy - Residentes Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/Wendy.png)

**Resumen de Entrevista:**

Wendy nos dice que la landing page de SecureID presenta la información de forma clara y accesible, con una navegación intuitiva que facilita encontrar lo necesario. El proceso de registro solicita datos personales detallados (nombre, apellidos, ID, dirección, teléfono, fecha de nacimiento, etc.), y la entrevistada considera que es fácil de entender y seguir paso a paso. Los íconos y botones son intuitivos y de fácil acceso, aunque sugiere que sería útil añadir funciones de interacción, como consultas o solicitudes de servicios específicos.

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 11:30 - 15:52

---

# Entrevista a Claudia Alejandra Aleman - Autoridades Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/claudia.png)

**Resumen de Entrevista:**

Claudia comenta respecto al landing page, la entrevistada destaco que el diseño es minimalista y fácil de comprender. Al hacerlo con las practicas del mercado hace que el usuario ya este acostumbrado a este tipo de navegación y este familiarizado con ello.  
Como vista de autoridad le pareció adecuado que la información este dividida por secciones y ítems, brindando la información necesaria para una leída rápida. Respecto al aplicativo móvil, comento que la navegación es intuitiva y sin retrasos al tocar y trasladarse a otras partes de la aplicación. Comparo experiencias pasadas donde no sabía dónde estaba una opción en especifico o que algunas veces la aplicación dejaba de funcionar. Respecto a la tecnología blockchain implementada, su opinión fue positiva ya que con las noticias que suceden últimamente le parece adecuado agregar estas tecnologías que brindan seguridad a ambas partes , al usuario y a la autoridad.

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 15:53 - 20:54

---

# Entrevista a Oscar Armas - Autoridades Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/oscar.png)

**Resumen de Entrevista:**

Oscar Armas, al interactuar con la landing page de SecureID, nos indica que tiene un diseño intuitivo y de fácil uso. Recalca que puede encontrar la información navegando en el navbar y que está concisa. Asimismo, agrega que el uso de animaciones en el inicio le pareció llamativo. Para la aplicación móvil, Oscar señala que es fácil de comprender su uso, ya que se puede buscar a los residentes de forma rápida ingresando su DNI o ID. Además, modificar su perfil le ayudaría a completar las solicitudes que son de su responsabilidad como autoridad local. Sobre la tecnología blockchain, menciona que es muy útil para la seguridad y protección de los datos de los residentes, ya que le permite tener un registro de todas las acciones que realiza y poder visualizarlo en el historial de transacciones. Por último, la agregación y modificación de los servicios es fundamental para una autoridad local, ya que le permite ofrecer a su comunidad (residentes) los beneficios de la institución municipal.

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 20:55 - 29:47

---

# Entrevista a Payda - Autoridades Locales

![image](./assets/7.3.2.RegistrodeEntrevistas/payda.png)

**Resumen de Entrevista:**

Se inicio la entrevista con una explicacion a la usuaria Payda representante de las autoriades locales, persona a fin al sector publico en la rama de salud, explicandole cual era el  funcionamiento de la aplicacion en desarrollo, asimismo se pidio su opinion en relacion a la factibilidad de implementacion no solo para la aceptacion por parte de los residentes de areas rurales, sino tambien para las mismas instituciones estatales que pudieran aceptar sacar informacion de aqui, explicando de la forma menos tecnica posible el funcionamiento de la tecnologia implementada a fin de que sea lo mas sencillo de entender para el usuario. DAndonos al final una interpretacion de que desde su punto de vista la aplicacion si podria tener buen futuro en el ambito que el representa.

Link de la entrevista: https://upcedupe-my.sharepoint.com/:v:/g/personal/u20211c186_upc_edu_pe/EancWiNePRdLrpEEaRmaqVMBKvwwwXIuFawZuMJ3sz6l6A?e=dhJE9L

Timing: 29:48 - 36:25

---

### 7.3.3. Evaluaciones según heurísticas
---

### UX Heuristics & Principles Evaluation

**Información General**

- Proyecto: SecureID
- Curso: Arquitecturas de Software Emergentes
- Vistas Evaluadas: Login, Registro, Identificación Digital, Servicios
- Escala de Severidad:
    1. Problema superficial.
    2. Problema menor.
    3. Problema mayor.
    4. Problema muy grave.

**Evaluación de Problemas**

| #  | Problema                                                                                 | Escala de Severidad | Heurística/Principio Violada(o)                   |
|----|------------------------------------------------------------------------------------------|---------------------|---------------------------------------------------|
| 1  | El proceso de registro no proporciona retroalimentación clara al usuario si falta información.                             | 3                   | Usabilidad: Visibilidad del Estado del Sistema       |
| 2  | La navegación en el menú de servicios es adecuada pero podría incluir una opción para consultas específicas. | 2                   | Usabilidad: Flexibilidad y Eficiencia de Uso       |
| 3  | Falta de personalización en los servicios disponibles según las necesidades del usuario.               | 2                   | Usabilidad: Control y Libertad del Usuario          |
| 4  | La interfaz de Identificación Digital es intuitiva, pero podría beneficiarse de más información contextual.               | 1                   | Diseño Estético y Minimalista          |
| 5  | En la sección de login, no se proporciona un mensaje claro cuando el usuario ingresa credenciales incorrectas.               | 3                   | Usabilidad: Visibilidad del Estado del Sistema          |

**Descripción de Problemas y Recomendaciones**

1. PROBLEMA #1: El proceso de registro no proporciona retroalimentación clara al usuario si falta información.
- Severidad: 3
- Heurística Violada: Usabilidad - Visibilidad del Estado del Sistema
- Descripción: Durante el proceso de registro, el usuario no recibe retroalimentación inmediata cuando omite un campo obligatorio, lo que puede generar confusión sobre si el registro fue exitoso o si falta información.
- Recomendación: Implementar mensajes de error en tiempo real que indiquen los campos obligatorios que faltan por completar, facilitando el flujo de registro.

    <img src="./assets/7.3.3.Evaluacionessegúnheurísticas/login.png" width="700"/>


2. PROBLEMA #2: La navegación en el menú de servicios es adecuada pero podría incluir una opción para consultas específicas.
- Severidad: 2
- Heurística Violada: Usabilidad - Flexibilidad y Eficiencia de Uso
- Descripción: La aplicación proporciona acceso a servicios mediante iconos, pero carece de opciones para consultas o solicitudes específicas, lo que limita la flexibilidad para el usuario.
- Recomendación: Añadir opciones de interacción, como consultas y solicitudes personalizadas en la sección de servicios, permitiendo a los usuarios acceder a servicios de acuerdo con sus necesidades.

    <img src="./assets/7.3.3.Evaluacionessegúnheurísticas/servicios.png" width="700"/>

3. PROBLEMA #3: Falta de personalización en los servicios disponibles según las necesidades del usuario.
- Severidad: 2
- Heurística Violada: Usabilidad - Control y Libertad del Usuario
- Descripción: Actualmente, la aplicación no permite a los usuarios personalizar la vista de servicios, lo cual puede afectar la eficiencia de uso.
- Recomendación: Permitir que los usuarios configuren los servicios según sus necesidades, destacando aquellos que son más relevantes para su perfil.

    <img src="./assets/7.3.3.Evaluacionessegúnheurísticas/servicios2.png" width="700"/>

4. PROBLEMA #4: La interfaz de Identificación Digital es intuitiva, pero podría beneficiarse de más información contextual.
- Severidad: 1
- Heurística Violada: Diseño Estético y Minimalista
- Descripción: La interfaz es clara y accesible, pero una mayor información contextual ayudaría a comprender mejor cada campo.
- Recomendación: Añadir descripciones breves o herramientas de ayuda en los campos clave de Identificación Digital, sin sobrecargar la interfaz.

    <img src="./assets/7.3.3.Evaluacionessegúnheurísticas/documento.png" width="700"/>

5. PROBLEMA #5: En la sección de login, no se proporciona un mensaje claro cuando el usuario ingresa credenciales incorrectas.
- Severidad: 3
- Heurística Violada: Usabilidad - Visibilidad del Estado del Sistema
- Descripción: Al ingresar credenciales incorrectas, no se muestra un mensaje claro de error, lo que puede confundir a los usuarios sobre si el error es del sistema o por datos incorrectos.
- Recomendación: Implementar mensajes de error específicos que indiquen que las credenciales son incorrectas, brindando claridad al usuario y mejorando la experiencia de inicio de sesión.

    <img src="./assets/7.3.3.Evaluacionessegúnheurísticas/inicio.png" width="700"/>

## 7.4. Video About-the-Product
---

<img src="./assets/7.4.VideoAbout-the-Product/abouttheproductvideo.png" width="700"/>

Link Microsoft Stream: https://upcedupe-my.sharepoint.com/personal/u20211c186_upc_edu_pe/_layouts/15/stream.aspx?id=%2Fpersonal%2Fu20211c186%5Fupc%5Fedu%5Fpe%2FDocuments%2FVideo%20About%2DThe%2DProduct%20%2D%20SecureID%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2Ea04fa467%2D0138%2D49c9%2D96c1%2D9c35b04b085b

Link YouTube: https://www.youtube.com/watch?v=1mA3r2Tlh-o

    Timing de inicio de cada integrante:

    Pastrana León, Aldo Francisco: 0:02 - 0:41

    Ore Aleman, Anderson Raul: 0:42 - 1:20

    Sabino Arostegui, Max Dayson: 1:21 - 2:06

    López Takahashi, Rodrigo Andrés: 2:07 - 2:44

    Hernandez Tuesta, Sebastian: 2:45 - 3:13
