# Capítulo IV: Strategic-Level Software Design

## 4.1. Strategic-Level Attribute-Driven Design

### 4.1.1. Design Purpose

### 4.1.2. Attribute-Driven Design Inputs

#### 4.1.2.1. Primary Functionality (Primary User Stories)
Esta sección describe los Epics e Historias de Usuario que tienen mayor impacto en la arquitectura de la solución SecureID. Estos requisitos funcionales son esenciales para el éxito del proyecto y deben ser considerados cuidadosamente durante el proceso de diseño.

| User Story ID | Título                                             | Descripción                                                                                                                                                                      | Criterios de aceptación                                                                                                  |
|---------------|----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| US09          | Implementación del Registro de Identidad en Blockchain | Como desarrollador backend, quiero implementar un servicio que registre las identidades de los usuarios en una blockchain privada para asegurar la inmutabilidad y seguridad de los datos. | • Dado que un usuario completa su registro, cuando los datos se envían al backend, entonces el sistema debe crear una entrada inmutable en la blockchain.  <br> • Dado que el registro es exitoso, cuando se consulta la identidad, entonces los datos deben coincidir exactamente con los registrados. |
| US11          | Verificación de Identidad en Tiempo Real          | Como desarrollador backend, quiero implementar un servicio de verificación de identidad en tiempo real que permita a las autoridades locales verificar la identidad de un usuario contra la blockchain. | • Dado que una autoridad local consulta la identidad de un usuario, cuando se envían los datos al backend, entonces el sistema debe verificar la identidad en la blockchain y devolver una respuesta en tiempo real.  <br> • Dado que la verificación es exitosa, cuando se recibe la respuesta, entonces debe indicar claramente la validez de la identidad. |
| US06          | Integración con Servicios Gubernamentales         | Como autoridad local, quiero que la plataforma SecureID esté integrada con los sistemas gubernamentales existentes para que pueda gestionar y verificar identidades de manera más eficiente. | • Dado que la plataforma está integrada, cuando realizo una consulta de identidad, entonces los datos se sincronizan y se verifican automáticamente con las bases de datos gubernamentales.  <br> • Dado que la integración es exitosa, cuando gestiono recursos o asistencia, entonces puedo realizar estas tareas de manera más eficiente y con menos errores. |
| US05          | Uso de la Plataforma sin Conexión a Internet       | Como residente de la zona rural, quiero poder usar la plataforma SecureID incluso cuando no tengo acceso a internet, para que mi identificación digital esté disponible en todo momento. | • Dado que no tengo conexión a internet, cuando uso la plataforma, entonces mis datos se almacenan localmente y se sincronizan con la blockchain cuando la conexión se restablezca.  <br> • Dado que la sincronización es exitosa, cuando reviso mi identificación digital, entonces los datos están actualizados y son consistentes. |
| US16          | Respaldo y Recuperación de Datos                   | Como desarrollador backend, quiero implementar un sistema robusto de respaldo y recuperación de datos para asegurar que la plataforma pueda recuperarse de fallos o pérdida de datos sin afectar la disponibilidad del servicio. | • Dado que ocurre una falla en el sistema, cuando se ejecuta el proceso de recuperación, entonces todos los datos deben ser restaurados a su estado más reciente sin pérdida significativa.  <br> • Dado que el sistema de respaldo está en funcionamiento, cuando se revisan los registros de backup, entonces deben mostrar que las copias de seguridad se realizan de manera regular y sin errores. |




#### 4.1.2.2. Quality attribute Scenarios
Los escenarios de atributos de calidad identificados inicialmente se centran en aquellos que tienen un mayor impacto en la arquitectura de nuestra solución. Estos escenarios proporcionan una visión clara de cómo se espera que nuestro sistema responda a diferentes estímulos en términos de calidad. 


|Atributo   | Fuente  | Estímulo  | Entorno  | Respuesta  | Medida |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|  Usabilidad | Residente rural  |  El usuario intenta registrarse en la plataforma SecureID. |  Conectividad limitada o en un dispositivo móvil básico. | El sistema proporciona una interfaz clara, accesible y con asistencia paso a paso.  | Registro completado sin errores o abandonos (95% éxito).  |
|Disponibilidad   |  Residente rural | El usuario intenta acceder a su identificación digital sin conexión a internet.  | Sin conexión a internet (offline). | El sistema almacena los datos localmente y sincroniza cuando hay conexión disponible.  | Identificación accesible en modo offline el 100% del tiempo.  |
|Rendimiento   | Autoridad local  |  La autoridad local verifica la identidad de un residente. | Plataforma con alto volumen de solicitudes.  | Verificación completada en menos de 2 segundos.  |  Tiempo de verificación inferior a 2 segundos en el 95% de los casos. |
| Seguridad  | Gobierno / Autoridad local  | Un intento de acceso no autorizado a la plataforma es detectado.  | Plataforma en operación normal.  |  El sistema detecta el acceso no autorizado, lo bloquea y notifica a los administradores. |  Tiempo de detección y respuesta inferior a 1 segundo. |
|Escalabilidad   |  Administrador del sistema |Aumento repentino en el número de registros de identificación.   | Alto crecimiento de usuarios en poco tiempo.  | El sistema gestiona el crecimiento sin degradación en el rendimiento.  |El sistema soporta el 100% del incremento de usuarios sin caída.  |
|  Privacidad | Residente rural  | El residente envía datos personales para su registro en la plataforma.  | Durante el proceso de registro en la plataforma.  | Los datos son cifrados y almacenados de manera segura, cumpliendo con normativas de privacidad (GDPR, CCPA).  | Cifrado de datos sensibles en tránsito y en reposo; cumplimiento del 100% de las normativas de privacidad aplicables.  |

#### 4.1.2.3. Constraints.
Los constraints son características que no pueden ser negociadas y están impuestas por el cliente o el negocio como guía para la elaboración de la solución. A continuación, se presentan los principales constraints a considerar en el diseño de nuestra solución.

| Technical Story ID  | Título  |  Descripción |  Criterios de Aceptación | Relacionado con (Epic ID)  |
| ------------ | ------------ | ------------ | ------------ | ------------ |
|TS01   | Cumplimiento de Normativas de Privacidad  |  La plataforma debe cumplir con normativas internacionales de protección de datos, como el GDPR, para garantizar la privacidad y seguridad de los usuarios. | Todos los datos personales deben ser cifrados y protegidos; auditorías de cumplimiento de normativas deben realizarse periódicamente.  |  US04, US09 |
| TS02  |  Funcionamiento Offline | La plataforma debe permitir el registro y acceso a datos sin conexión a internet, sincronizando la información cuando se restablezca la conectividad.  |Los usuarios pueden registrar y consultar su identidad digital offline; los datos se sincronizan automáticamente una vez que la conexión a internet esté disponible.   | US05, US10  |
|TS03  |  Escalabilidad |El sistema debe ser escalable para manejar un crecimiento exponencial de usuarios sin afectar el rendimiento o la disponibilidad de los servicios.   |  El sistema debe soportar hasta 1 millón de usuarios simultáneos sin reducir su rendimiento; monitoreo de escalabilidad debe realizarse continuamente para ajustes en infraestructura. |  US08, US14 |
|  TS04 |  Integración con Sistemas Gubernamentales | SecureID debe integrarse con bases de datos y sistemas de servicios gubernamentales para validar la identidad de los usuarios y permitir el acceso a servicios.  |Las autoridades locales pueden acceder a los datos de los residentes a través de la integración con bases de datos gubernamentales; sincronización de datos correcta en tiempo real.   |  US06, US12 |
| TS05  |  Seguridad de Datos y Auditoría | La plataforma debe mantener un registro detallado de todas las transacciones e interacciones para auditorías de seguridad.  | Cada acción dentro de la plataforma debe generar un registro que puede ser auditado; el sistema debe detectar intentos de fraude y alertar a las autoridades locales en tiempo real.  | US04, US15  |
### 4.1.3. Architectural Drivers Backlog
---
### 4.1.4. Architectural Design Decisions
---
### 4.1.5. Quality Attribute Scenario Refinements
---
## 4.2. Strategic-Level Domain-Driven Design
---
### 4.2.1. EventStorming
---
### 4.2.2. Candidate Context Discovery
---
### 4.2.3. Domain Message Flows Modeling
---
### 4.2.4. Bounded Context Canvases
---
### 4.2.5. Context Mapping
---
## 4.3. Software Architecture
---
### 4.3.1. Software Architecture System Landscape Diagram
---
### 4.3.2. Software Architecture Context Level Diagrams
---
### 4.3.3. Software Architecture Container Level Diagrams
---
### 4.3.4. Software Architecture Deployment Diagrams
---