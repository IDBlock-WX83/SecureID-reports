# Capítulo IV: Strategic-Level Software Design
---
## 4.1. Strategic-Level Attribute-Driven Design
---
### 4.1.1. Design Purpose
---
### 4.1.2. Attribute-Driven Design Inputs
---
#### 4.1.2.1. Primary Functionality (Primary User Stories)
---
#### 4.1.2.2. Quality attribute Scenarios
---
#### 4.1.2.3. Constraints.
---
### 4.1.3. Architectural Drivers Backlog
---
### 4.1.4. Architectural Design Decisions
---
### 4.1.5. Quality Attribute Scenario Refinements

<table> <tr> <th colspan="3" valign="top">Scenario Refinement for Scenario 1</th> </tr> <tr> <td colspan="2" valign="top">Scenario(s):</td> <td valign="top">Verificación de Identidad en Tiempo Real (US02, US11)</td> </tr> <tr> <td colspan="2" valign="top">Business Goals:</td> <td valign="top">Garantizar que las autoridades locales puedan verificar la identidad de los residentes de manera eficiente y precisa.</td> </tr> <tr> <td colspan="2" valign="top">Relevant Quality Attributes:</td> <td valign="top">Rendimiento, Disponibilidad, Precisión</td> </tr> <tr> <td rowspan="6" valign="top"> <p></p> <p></p> <p>Scenario Components</p> </td> <td valign="top">Stimulus:</td> <td valign="top">Solicitud de verificación de identidad por parte de una autoridad local.</td> </tr> <tr> <td valign="top">Stimulus Source:</td> <td valign="top">Autoridad local utilizando la plataforma SecureID.</td> </tr> <tr> <td valign="top">Environment:</td> <td valign="top">Entorno de producción con alta carga de usuarios.</td> </tr> <tr> <td valign="top">Artifact (if Known)</td> <td valign="top">Servicio backend de verificación de identidad y blockchain.</td> </tr> <tr> <td valign="top">Response:</td> <td valign="top">Verificación precisa y respuesta en tiempo real.</td> </tr> <tr> <td valign="top">Response Measure:</td> <td valign="top">Tiempo de respuesta menor a 2 segundos y precisión del 100% en la verificación.</td> </tr> <tr> <td colspan="2" valign="top">Questions:</td> <td valign="top">¿Cómo se manejarán los picos de carga? ¿Qué ocurre si hay problemas de conectividad?</td> </tr> <tr> <td colspan="2" valign="top"> <p>Issues:</p> <p></p> </td> <td valign="top">a necesidad de manejar grandes volúmenes de solicitudes en tiempo real podría afectar la disponibilidad y rendimiento del sistema</td> </tr> </table>

<table> <tr> <th colspan="3" valign="top">Scenario Refinement for Scenario 2</th> </tr> <tr> <td colspan="2" valign="top">Scenario(s):</td> <td valign="top">Sincronización de Datos en Modo Offline (US05, US10)</td> </tr> <tr> <td colspan="2" valign="top">Business Goals:</td> <td valign="top">Permitir que los residentes de zonas rurales usen la plataforma SecureID incluso sin conexión a internet.</td> </tr> <tr> <td colspan="2" valign="top">Relevant Quality Attributes:</td> <td valign="top">Fiabilidad, Integridad de Datos</td> </tr> <tr> <td rowspan="6" valign="top"> <p></p> <p></p> <p>Scenario Components</p> </td> <td valign="top">Stimulus:</td> <td valign="top">Intento de sincronización de datos cuando se restablece la conexión a internet.</td> </tr> <tr> <td valign="top">Stimulus Source:</td> <td valign="top">Residente que estaba trabajando en modo offline.</td> </tr> <tr> <td valign="top">Environment:</td> <td valign="top">Zona rural con conexión inestable.</td> </tr> <tr> <td valign="top">Artifact (if Known)</td> <td valign="top">Mecanismo de sincronización de datos local y blockchain.</td> </tr> <tr> <td valign="top">Response:</td> <td valign="top">Sincronización exitosa de los datos locales con la blockchain.</td> </tr> <tr> <td valign="top">Response Measure:</td> <td valign="top">Sincronización completa sin pérdida de datos y confirmación de éxito en menos de 5 minutos.</td> </tr> <tr> <td colspan="2" valign="top">Questions:</td> <td valign="top">¿Cómo se manejarán los conflictos de datos durante la sincronización? ¿Qué ocurre si la conexión sigue siendo intermitente?</td> </tr> <tr> <td colspan="2" valign="top"> <p>Issues:</p> <p></p> </td> <td valign="top">El manejo de datos conflictivos y la garantía de integridad en entornos con conexión intermitente pueden ser desafiantes</td> </tr> </table>

<table> <tr> <th colspan="3" valign="top">Scenario Refinement for Scenario 3</th> </tr> <tr> <td colspan="2" valign="top">Scenario(s):</td> <td valign="top">Gestión de Permisos y Acceso a Datos (US13)</td> </tr> <tr> <td colspan="2" valign="top">Business Goals:</td> <td valign="top">Asegurar que solo los usuarios autorizados puedan acceder y modificar datos sensibles en la plataforma.</td> </tr> <tr> <td colspan="2" valign="top">Relevant Quality Attributes:</td> <td valign="top">Seguridad, Control de Acceso</td> </tr> <tr> <td rowspan="6" valign="top"> <p></p> <p></p> <p>Scenario Components</p> </td> <td valign="top">Stimulus:</td> <td valign="top">Solicitud de acceso a datos sensibles por parte de un usuario.</td> </tr> <tr> <td valign="top">Stimulus Source:</td> <td valign="top">Usuario que intenta acceder a datos en la plataforma.</td> </tr> <tr> <td valign="top">Environment:</td> <td valign="top">Entorno seguro con políticas de control de acceso en vigor.</td> </tr> <tr> <td valign="top">Artifact (if Known)</td> <td valign="top">Sistema de gestión de permisos y backend de acceso a datos.</td> </tr> <tr> <td valign="top">Response:</td> <td valign="top">Acceso concedido o denegado según los permisos del usuario.</td> </tr> <tr> <td valign="top">Response Measure:</td> <td valign="top">Tiempo de respuesta para la verificación de permisos menor a 2 segundos y precisión en el control de acceso del 100%.</td> </tr> <tr> <td colspan="2" valign="top">Questions:</td> <td valign="top">¿Cómo se manejarán los permisos en caso de cambios de roles? ¿Qué medidas se tomarán para evitar accesos no autorizados?</td> </tr> <tr> <td colspan="2" valign="top"> <p>Issues:</p> <p></p> </td> <td valign="top">Garantizar que el sistema de permisos esté siempre actualizado y que las auditorías detecten cualquier acceso no autorizado puede ser complejo.</td> </tr> </table>

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