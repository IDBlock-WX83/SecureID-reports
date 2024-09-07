# Capítulo III: Requirements Specification
---
## 3.1. To-Be Scenario Mapping
---
## Residentes de zonas rurales:
[![zonas-rurales-to-be.png](https://i.postimg.cc/zvKJKMKW/zonas-rurales-to-be.png)](https://postimg.cc/MfZ289sK)

## Autoridades locales:
[![autoridades-locales-tobe.png](https://i.postimg.cc/kXJZxzQm/autoridades-locales-tobe.png)](https://postimg.cc/8sYtGyXK)

## 3.2. User Stories

Plataforma SecureID
---
| **Número** | US01 |
|------------|------|
| **Usuarios** | Residente de la zona rural |
| **Nombre de Historia** | Registro de Identificación Digital |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de la zona rural, quiero registrar mi identificación digital en la plataforma SecureID para acceder a servicios esenciales como salud, educación y asistencia social. |
| **Criterios de Aceptación** | • Dado que soy un nuevo usuario en la plataforma, cuando ingreso mis datos personales en la interfaz, entonces se crea un registro seguro e inmutable en la blockchain.<br>• Dado que completé mi registro, cuando accedo a mi perfil, entonces puedo ver mi identificación digital y los servicios asociados disponibles. |

---
---

| **Número** | US02 |
|------------|------|
| **Usuarios** | Autoridades locales |
| **Nombre de Historia** | Verificación de Identidad |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como autoridad local, quiero verificar la identidad digital de los residentes a través de la plataforma SecureID para asegurarme de que pueden acceder a los recursos y servicios sin fraude. |
| **Criterios de Aceptación** | • Dado que estoy autenticado en la plataforma como autoridad local, cuando ingreso los datos de un residente, entonces puedo verificar su identidad a través de un registro seguro en la blockchain.<br>• Dado que he verificado la identidad de un residente, cuando apruebo su solicitud, entonces el residente puede acceder a los servicios para los que está calificado. |

---
---

| **Número** | US03 |
|------------|------|
| **Usuarios** | Residente de la zona rural |
| **Nombre de Historia** | Acceso a Servicios Esenciales |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de la zona rural, quiero acceder a servicios como salud, educación y asistencia social a través de la plataforma SecureID utilizando mi identificación digital. |
| **Criterios de Aceptación** | • Dado que tengo una identificación digital en la plataforma, cuando la presento para acceder a un servicio, entonces el servicio se habilita si mi identidad es verificada correctamente.<br>• Dado que he accedido a un servicio utilizando la plataforma, cuando completo el proceso, entonces puedo recibir confirmación del servicio utilizado y mantener un registro de mis interacciones. |

---
---
| **Número** | US04 |
|------------|------|
| **Usuarios** | Desarrolladores de SecureID |
| **Nombre de Historia** | Seguridad y Protección de Datos |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador de la plataforma SecureID, quiero implementar medidas avanzadas de seguridad para proteger los datos personales de los usuarios y asegurar que la información almacenada en la blockchain no pueda ser alterada o comprometida. |
| **Criterios de Aceptación** | • Dado que los datos se almacenan en la blockchain, cuando se realizan cambios o se agregan nuevos datos, entonces estos deben estar encriptados y ser inmutables.<br>• Dado que hemos implementado medidas de seguridad, cuando se realizan auditorías de seguridad, entonces los datos deben permanecer seguros y protegidos contra accesos no autorizados. |

---
---

| **Número** | US05 |
|------------|------|
| **Usuarios** | Residente de la zona rural |
| **Nombre de Historia** | Uso de la Plataforma sin Conexión a Internet |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de la zona rural, quiero poder usar la plataforma SecureID incluso cuando no tengo acceso a internet, para que mi identificación digital esté disponible en todo momento. |
| **Criterios de Aceptación** | • Dado que no tengo conexión a internet, cuando uso la plataforma, entonces mis datos se almacenan localmente y se sincronizan con la blockchain cuando la conexión se restablezca.<br>• Dado que la sincronización es exitosa, cuando reviso mi identificación digital, entonces los datos están actualizados y son consistentes. |

---
---

| **Número** | US06 |
|------------|------|
| **Usuarios** | Autoridades locales |
| **Nombre de Historia** | Integración con Servicios Gubernamentales |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como autoridad local, quiero que la plataforma SecureID esté integrada con los sistemas gubernamentales existentes para que pueda gestionar y verificar identidades de manera más eficiente. |
| **Criterios de Aceptación** | • Dado que la plataforma está integrada, cuando realizo una consulta de identidad, entonces los datos se sincronizan y se verifican automáticamente con las bases de datos gubernamentales.<br>• Dado que la integración es exitosa, cuando gestiono recursos o asistencia, entonces puedo realizar estas tareas de manera más eficiente y con menos errores. |

---
---

| **Número** | US07 |
|------------|------|
| **Usuarios** | Residente de la zona rural |
| **Nombre de Historia** | Interfaz de Usuario Accesible |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de la zona rural con bajo nivel de alfabetización digital, quiero una interfaz de usuario que sea simple y fácil de usar para que pueda gestionar mi identificación digital sin dificultad. |
| **Criterios de Aceptación** | • Dado que accedo a la plataforma con conocimientos tecnológicos limitados, cuando uso la interfaz, entonces puedo navegar fácilmente y completar tareas sin complicaciones.<br>• Dado que la interfaz es accesible, cuando uso la plataforma, entonces recibo orientación clara y visual que me ayuda a gestionar mi identificación digital. |

---
---

| **Número** | US08 |
|------------|------|
| **Usuarios** | Desarrolladores de SecureID |
| **Nombre de Historia** | Escalabilidad de la Plataforma |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador de la plataforma SecureID, quiero asegurarme de que la plataforma sea escalable para que pueda manejar un gran número de usuarios y transacciones sin afectar el rendimiento. |
| **Criterios de Aceptación** | • Dado que la plataforma necesita soportar a muchos usuarios, cuando se realizan pruebas de carga, entonces el sistema debe mantener un rendimiento óptimo sin caídas.<br>• Dado que la escalabilidad es crítica, cuando se añade infraestructura adicional, entonces la plataforma debe continuar operando sin problemas. |

---

User Stories para el desarrollo del servicio Backend:
---

| **Número** | US09 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Implementación del Registro de Identidad en Blockchain |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador backend, quiero implementar un servicio que registre las identidades de los usuarios en una blockchain privada para asegurar la inmutabilidad y seguridad de los datos. |
| **Criterios de Aceptación** | • Dado que un usuario completa su registro, cuando los datos se envían al backend, entonces el sistema debe crear una entrada inmutable en la blockchain.<br>• Dado que el registro es exitoso, cuando se consulta la identidad, entonces los datos deben coincidir exactamente con los registrados. |

---
---

| **Número** | US10 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Sincronización de Datos en Modo Offline |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como desarrollador backend, quiero crear un mecanismo de sincronización que permita a los usuarios almacenar datos localmente cuando están offline y sincronizarlos con la blockchain cuando se restablezca la conexión. |
| **Criterios de Aceptación** | • Dado que un usuario utiliza la plataforma sin conexión, cuando vuelve a estar en línea, entonces los datos almacenados localmente deben sincronizarse automáticamente con la blockchain.<br>• Dado que la sincronización es exitosa, cuando se verifica la identidad, entonces los datos deben estar actualizados y ser consistentes. |

---
---

| **Número** | US11 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Verificación de Identidad en Tiempo Real |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador backend, quiero implementar un servicio de verificación de identidad en tiempo real que permita a las autoridades locales verificar la identidad de un usuario contra la blockchain. |
| **Criterios de Aceptación** | • Dado que una autoridad local consulta la identidad de un usuario, cuando se envían los datos al backend, entonces el sistema debe verificar la identidad en la blockchain y devolver una respuesta en tiempo real.<br>• Dado que la verificación es exitosa, cuando se recibe la respuesta, entonces debe indicar claramente la validez de la identidad. |

---
---

| **Número** | US12 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Integración con Bases de Datos Gubernamentales |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador backend, quiero crear APIs que integren la plataforma SecureID con bases de datos gubernamentales existentes para facilitar la verificación de identidades y el acceso a servicios. |
| **Criterios de Aceptación** | • Dado que se realiza una solicitud de verificación, cuando el backend se comunica con la base de datos gubernamental, entonces los datos deben ser sincronizados y verificados de manera automática.<br>• Dado que la integración es exitosa, cuando se completa la verificación, entonces el sistema debe proporcionar una respuesta en un tiempo razonable y con alta precisión. |

---
---

| **Número** | US13 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Gestión de Permisos y Acceso a Datos |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como desarrollador backend, quiero implementar un sistema de gestión de permisos que controle quién puede acceder y modificar los datos en la plataforma, asegurando la seguridad y privacidad de la información. |
| **Criterios de Aceptación** | • Dado que un usuario intenta acceder a datos sensibles, cuando realiza la solicitud, entonces el sistema debe verificar si tiene los permisos adecuados antes de conceder acceso.<br>• Dado que la gestión de permisos es efectiva, cuando se realizan auditorías, entonces no deben encontrarse accesos no autorizados. |

---
---

| **Número** | US14 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Escalabilidad del Sistema |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador backend, quiero diseñar la arquitectura del sistema de manera que sea escalable, permitiendo que la plataforma maneje un número creciente de usuarios y transacciones sin pérdida de rendimiento. |
| **Criterios de Aceptación** | • Dado que la plataforma recibe un aumento en la cantidad de usuarios, cuando se realizan pruebas de carga, entonces el sistema debe mantener un rendimiento óptimo sin caídas.<br>• Dado que la escalabilidad es crítica, cuando se implementa infraestructura adicional, entonces la plataforma debe continuar funcionando sin problemas. |

---
---

| **Número** | US15 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Implementación de Logs y Auditorías de Seguridad |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como desarrollador backend, quiero implementar un sistema de logs detallado y capacidades de auditoría para monitorear todas las transacciones y accesos en la plataforma, garantizando la seguridad y transparencia. |
| **Criterios de Aceptación** | • Dado que se realiza cualquier operación en la plataforma, cuando se genera un log, entonces debe contener detalles completos de la operación, incluyendo quién la realizó y cuándo.<br>• Dado que se realiza una auditoría, cuando se revisan los logs, entonces deben estar completos y ser coherentes, reflejando todas las operaciones sin omisiones. |

---
---

| **Número** | US16 |
|------------|------|
| **Usuarios** | Desarrolladores Backend |
| **Nombre de Historia** | Respaldo y Recuperación de Datos |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Alto |
| **Descripción** | Como desarrollador backend, quiero implementar un sistema robusto de respaldo y recuperación de datos para asegurar que la plataforma pueda recuperarse de fallos o pérdida de datos sin afectar la disponibilidad del servicio. |
| **Criterios de Aceptación** | • Dado que ocurre una falla en el sistema, cuando se ejecuta el proceso de recuperación, entonces todos los datos deben ser restaurados a su estado más reciente sin pérdida significativa.<br>• Dado que el sistema de respaldo está en funcionamiento, cuando se revisan los registros de backup, entonces deben mostrar que las copias de seguridad se realizan de manera regular y sin errores. |

---

User stories para el Landing Page:
---

| **Número** | US17 |
|------------|------|
| **Usuarios** | Visitantes del sitio web |
| **Nombre de Historia** | Visualización de la Propuesta de Valor |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Bajo |
| **Descripción** | Como visitante de la landing page, quiero entender rápidamente la propuesta de valor de SecureID para saber cómo esta plataforma puede ayudarme a obtener una identificación digital segura. |
| **Criterios de Aceptación** | • Dado que accedo a la landing page, cuando leo el encabezado y el mensaje principal, entonces debería entender claramente la propuesta de valor de la plataforma.<br>• Dado que la propuesta de valor está bien comunicada, cuando navego por la página, entonces la información debe ser concisa y fácil de entender. |

---
---

| **Número** | US18 |
|------------|------|
| **Usuarios** | Residentes de zonas rurales |
| **Nombre de Historia** | Información sobre los Beneficios de SecureID |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de una zona rural, quiero conocer los beneficios de usar SecureID para entender cómo puede mejorar mi acceso a servicios esenciales. |
| **Criterios de Aceptación** | • Dado que soy un visitante de la landing page, cuando navego por la sección de beneficios, entonces debería ver información detallada sobre cómo SecureID mejora el acceso a salud, educación y asistencia social.<br>• Dado que los beneficios están claramente descritos, cuando termino de leer la sección, entonces debería tener una comprensión clara de cómo SecureID me puede beneficiar. |

---
---

| **Número** | US19 |
|------------|------|
| **Usuarios** | Autoridades locales |
| **Nombre de Historia** | Información sobre Integración con Sistemas Gubernamentales |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como autoridad local, quiero ver información sobre cómo SecureID se integra con los sistemas gubernamentales para asegurarme de que puede ser implementado fácilmente en mi comunidad. |
| **Criterios de Aceptación** | • Dado que soy una autoridad local visitando la landing page, cuando accedo a la sección técnica, entonces debería encontrar detalles sobre la integración con bases de datos gubernamentales.<br>• Dado que la información técnica está disponible, cuando la reviso, entonces debería entender claramente cómo la plataforma se integrará con los sistemas existentes. |

---
---

| **Número** | US20 |
|------------|------|
| **Usuarios** | Residentes de zonas rurales |
| **Nombre de Historia** | Acceso a Recursos Educativos |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como residente de una zona rural, quiero acceder a recursos educativos en la plataforma SecureID para aprender a utilizarla de manera efectiva. |
| **Criterios de Aceptación** | • Dado que soy un nuevo usuario, cuando accedo a la sección de recursos educativos, entonces debería encontrar tutoriales y guías que me ayuden a entender cómo usar la plataforma.<br>• Dado que los recursos educativos están disponibles, cuando los utilizo, entonces debería ser capaz de navegar y completar tareas relacionadas con mi identificación digital. |

---

---

| **Número** | US21 |
|------------|------|
| **Usuarios** | Visitantes del sitio web |
| **Nombre de Historia** | Llamado a la Acción para Registro |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Bajo |
| **Descripción** | Como visitante de la landing page, quiero ver un claro llamado a la acción para registrarme en SecureID y comenzar a utilizar la plataforma. |
| **Criterios de Aceptación** | • Dado que estoy navegando la landing page, cuando llego al llamado a la acción, entonces debería ver un botón prominente y claro que me invite a registrarme.<br>• Dado que el llamado a la acción es efectivo, cuando hago clic en él, entonces debería ser dirigido a la página de registro de manera fluida. |

---
---

| **Número** | US22 |
|------------|------|
| **Usuarios** | Visitantes del sitio web |
| **Nombre de Historia** | Optimización para Dispositivos Móviles |
| **Prioridad en Negocio** | Alta |
| **Riesgo en Desarrollo** | Medio |
| **Descripción** | Como visitante de la landing page, quiero que la página esté optimizada para dispositivos móviles para poder navegarla cómodamente desde mi teléfono o tableta. |
| **Criterios de Aceptación** | • Dado que estoy accediendo a la landing page desde un dispositivo móvil, cuando navego por el sitio, entonces la página debe adaptarse perfectamente a la pantalla y ser fácil de usar.<br>• Dado que la optimización móvil es exitosa, cuando interactúo con la página en mi teléfono, entonces debería tener una experiencia fluida y sin problemas. |

---
## 3.3. Impact Mapping


### Residentes de zonas rurales:
[![residendete-rurarles-impact-mapping.png](https://i.postimg.cc/DZDQpC0B/residendete-rurarles-impact-mapping.png)](https://postimg.cc/R67nNLcH)

### Autoridades locales:
[![autoridades-locales-impact-mapping.png](https://i.postimg.cc/tJx3KhVy/autoridades-locales-impact-mapping.png)](https://postimg.cc/YLtLgL3y)

## 3.4. Product Backlog
---

**Técnica Utilizada: Números de Fibonacci**  
Los números de Fibonacci (1, 2, 3, 5, 8, 13, etc.) se utilizan para representar el tamaño relativo del esfuerzo necesario para completar cada historia de usuario. Las historias que tienen una complejidad o esfuerzo mayor reciben un número más alto, mientras que las más sencillas reciben un número más bajo.

| Número de Historia | Descripción                                            | Estimación (Fibonacci) |
|--------------------|--------------------------------------------------------|------------------------|
| **US04**           | Seguridad y Protección de Datos                        | 13                     |
| **US06**           | Integración con Servicios Gubernamentales              | 13                     |
| **US08**           | Escalabilidad de la Plataforma                         | 13                     |
| **US09**           | Implementación del Registro de Identidad en Blockchain | 13                     |
| **US11**           | Verificación de Identidad en Tiempo Real               | 13                     |
| **US12**           | Integración con Bases de Datos Gubernamentales         | 13                     |
| **US14**           | Escalabilidad del Sistema                              | 13                     |
| **US16**           | Respaldo y Recuperación de Datos                       | 13                     |
| **US01**           | Registro de Identificación Digital                     | 8                      |
| **US02**           | Verificación de Identidad                              | 8                      |
| **US05**           | Uso de la Plataforma sin Conexión a Internet           | 8                      |
| **US10**           | Sincronización de Datos en Modo Offline                | 8                      |
| **US13**           | Gestión de Permisos y Acceso a Datos                   | 8                      |
| **US15**           | Implementación de Logs y Auditorías de Seguridad       | 8                      |
| **US22**           | Optimización para Dispositivos Móviles                 | 8                      |
| **US03**           | Acceso a Servicios Esenciales                          | 5                      |
| **US07**           | Interfaz de Usuario Accesible                          | 5                      |
| **US19**           | Información sobre Integración con Sistemas Gubernamentales | 5                  |
| **US17**           | Visualización de la Propuesta de Valor                 | 3                      |
| **US18**           | Información sobre los Beneficios de SecureID           | 3                      |
| **US20**           | Testimonios y Casos de Éxito                           | 3                      |
| **US21**           | Llamado a la Acción para Registro                      | 2                      |
