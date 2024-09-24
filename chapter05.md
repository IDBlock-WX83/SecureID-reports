# Capítulo V: Tactical-Level Software Design

## 5.1. Bounded Context: Profile Management

### 5.1.1. Domain Layer
Aggregates

|Nombre|Categoría|Propósito|
| :- | :- | :- |
|Profile|root|Representa el perfil digital del usuario, central en la gestión de perfiles, incluye información personal.|
|ProfileHistory|Supporting Aggregate|Almacena el historial de cambios o actualizaciones realizadas en el perfil.|

Attributes

Profile

|Name|Data Type|Visibility|Description|
| :- | :- | :- | :- |
|profileID|UUID|Private|Identificador unico|
|name|String|Public|Nombre complete del usuario.|
|email|String|Public|Correo del usuario|
|phoneNumber|String|Public|Numero de contacto del usuario|
|address|String|Public|Direccion del usuario|
|dateOfBirth|Date|Public|Fecha de nacimiento|
|profileStatus|Enum (Active, Inactive, Deleted)|Private|Estado del usuario (active, inactive, eliminado)|

ProfileHistory

|Nombre|Tipo de Dato|Visibilidad|Descripción|
| :- | :- | :- | :- |
|changeID|UUID|private|ID único para cada registro de cambio.|
|changeType|Enum (Update, Delete, Create)|private|Tipo de cambio realizado en el perfil.|
|changeDate|DateTime|private|Fecha y hora en que se realizó el cambio.|
|changedBy|String|private|Usuario o entidad del sistema que realizó el cambio.|

Methods

Profile

|Nombre|Tipo de Retorno|Visibilidad|Descripción|
| :- | :- | :- | :- |
|registerProfile|void|public|Método para registrar un nuevo perfil de usuario con los campos requeridos (nombre, correo, etc.).|
|updateProfile|void|public|Actualiza los detalles del perfil existente, como el nombre o la dirección.|
|deleteProfile|void|public|Marca el perfil como eliminado, cambia el estado a "Eliminado".|
|activateProfile|void|public|Reactiva un perfil previamente inactivo.|
|getProfileStatus|Enum|public|Retorna el estado actual del perfil (Activo, Inactivo, Eliminado).|

ProfileHistory

|Nombre|Tipo de Retorno|Visibilidad|Descripción|
| :- | :- | :- | :- |
|logChange|void|private|Registra un cambio (crear, actualizar, eliminar) en el perfil con detalles relevantes.|
|getChangeHistory|List<ProfileHistory>|public|Recupera el historial de cambios realizados en un perfil específico.|

### 5.1.2. Interface Layer

Controllers

|Nombre|Categoría|Propósito|
| :- | :- | :- |
|ProfileController|RESTful API|Controlador principal para gestionar las operaciones del perfil de usuario (registro, actualización, eliminación).|
|ProfileHistoryController|RESTful API|Controlador para acceder al historial de cambios de los perfiles de usuario.|

Methods

ProfileController

|Name|Return Type|Visibility|Description|
| :- | :- | :- | :- |
|registerProfile|ProfileItem|Public|Crea un nuevo perfil en el sistema y devuelve el identificador único del perfil creado.|
|updateProfile|ProfileItem|Public|Actualiza los detalles del perfil según los datos proporcionados (nombre, correo, dirección, etc.).|
|deleteProfile|ProfileItem|Public|Marca el perfil como eliminado en el sistema y retorna un mensaje de confirmación.|
|activateProfile|ProfileItem|Public|Reactiva un perfil que estaba previamente inactivo.|
|getProfile|ProfileItem |Public|Recupera los detalles completos de un perfil específico por su ID.|

ProfileHistoryController

|Name|Return Type|Visibility|Description|
| :- | :- | :- | :- |
|getProfileHistory|ProfileItem|Public|Recupera el historial de cambios realizados en un perfil específico basado en su ID.|
|registerProfileHistoryChange|ProfileItem|Private|Registra un nuevo cambio en el historial de un perfil.|

### 5.1.3. Application Layer

Handlers

|Name|Category|Purpose|
| :- | :- | :- |
|ProfileCommandHandler|Command Handler|Gestiona los comandos relacionados con la creación, actualización y eliminación de perfiles.|
|ProfileQueryHandler|Query Handler|Se encarga de procesar consultas para recuperar datos de los perfiles, como el historial y los detalles de los perfiles.|

Atributes

**ProfileCommandHandler**

|Name|Data Type|Visibility|Description|
| :- | :- | :- | :- |
|profileRepository|ProfileRepository|Private|Repositorio para acceder y gestionar la información del perfil.|
|eventBus|EventBus|Private|Utilizado para publicar eventos cuando se realiza una acción en el perfil (p. ej., cuando se crea o elimina).|

**ProfileQueryHandler**

|Name|Data Type|Visibility|Description|
| :- | :- | :- | :- |
|profileRepository|ProfileRepository|Private|Repositorio que permite acceder a la información del perfil para las consultas.|
|profileHistoryRepository|ProfileHistoryRepository|Private|Repositorio que permite acceder al historial de cambios de los perfiles.|

### 5.1.4. Infrastructure Layer

Repository

|Name|Category|Purpose|
| :- | :- | :- |
|ProfileRepository|Data Repository|Maneja la persistencia y recuperación de los datos del perfil en la base de datos.|
|ProfileHistoryRepository|Data Repository|Se encarga de almacenar y recuperar el historial de modificaciones realizadas en los perfiles de los usuarios.|
|EventStoreRepository|Event Repository|Almacena y gestiona los eventos relacionados con las acciones de perfil, como la creación o eliminación.|

Atributes

ProfileRepository

|Name|Data Type|Visibility|Description|
| :- | :- | :- | :- |
|dbContext|DbContext|Private|Objeto que maneja las operaciones de base de datos y proporciona acceso a la información de los perfiles.|
|logger|ILogger|Private|Para registrar actividades o errores que ocurren durante las operaciones de la base de datos.|

ProfileHistoryRepository

|Name|Data Type|Visibility|Description|
| :- | :- | :- | :- |
|dbContext|DbContext|Private|Proporciona acceso a la base de datos para el historial de modificaciones de los perfiles.|
|logger|ILogger|Private|Registra eventos o errores que ocurren durante la gestión del historial de perfiles.|

### 5.1.6. Bounded Context Software Architecture Component Level Diagrams

![](assets/chapter5/1/1_architecture.png)

### 5.1.7. Bounded Context Software Architecture Code Level Diagrams

#### 5.1.7.1. Bounded Context Domain Layer Class Diagrams

![](assets/chapter5/1/1_class.png)

#### 5.1.7.2. Bounded Context Database Design Diagram

![](assets/chapter5/1/1_database.png)

## 5.2. Bounded Context: Identity Verification

### 5.2.1. Domain Layer

Aggregate

|Name|Category|Purpose|
| :- | :- | :- |
|IdentityVerification|Aggregate|Gestionar el proceso de verificación de identidad.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|verification\_id|varchar|Public|Identificador único de la verificación de identidad.|
|profile\_id|varchar|Private|Identificador del usuario cuya identidad se verifica.|
|status|varchar|Public|Estado de la verificación (Pendiente, Aprobada, Rechazada).|
|verification\_date|timestamp|Private|Fecha en la que se realizó la verificación.|
|created\_at|timestamp|Private|Marca de tiempo de creación del registro.|
|updated\_at|timestamp|Private|Marca de tiempo de la última actualización.|

Methods

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|initiateVerification|void|Public|Inicia el proceso de verificación de identidad.|
|checkVerificationStatus|varchar|Public|Verifica y retorna el estado actual de la verificación.|
|approveVerification|void|Public|Aprueba la verificación de identidad.|
|rejectVerification|void|Public|Rechaza la verificación de identidad.|
|logVerificationAttempt|void|Private|Registra un intento de verificación.|


### 5.2.2. Interface Layer

Controller

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|IdentityVerificationController|Controller|Manejar las solicitudes relacionadas con la verificación de identidad.|

Methods

|**Name**|**Return Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|initiateVerification|void|Public|Inicia el proceso de verificación de identidad para un usuario.|
|checkVerificationStatus|string|Public|Devuelve el estado actual de la verificación de identidad.|
|approveVerification|void|Public|Aprueba la verificación de identidad y actualiza el estado.|
|rejectVerification|void|Public|Rechaza la verificación de identidad y actualiza el estado.|
|logVerificationAttempt|void|Private|Registra un intento de verificación para auditoría.|


### 5.2.3. Application Layer

Handler

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|IdentityVerificationHandler|Command Handler|Manejar la lógica de negocio para la verificación de identidad.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|profileId|integer|Public|ID del usuario cuya identidad se está verificando.|
|verificationStatus|string|Private|Estado actual de la verificación (Ej. Pendiente, Aprobado, Rechazado).|
|verificationRequestDate|timestamp|Private|Fecha y hora en que se realizó la solicitud de verificación.|
|verificationAttemptLogs|list|Private|Registros de intentos de verificación realizados.|
|externalVerificationService|string|Private|Servicio externo utilizado para la verificación de identidad.|



### 5.2.4. Infrastructure Layer

Repository

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|IdentityVerificationRepository|Repository|Almacenar y gestionar datos relacionados con las verificaciones de identidad.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|id|integer|Public|ID único de la verificación de identidad.|
|profileId|integer|Public|ID del usuario cuya identidad ha sido verificada.|
|verificationStatus|string|Public|Estado de la verificación (Ej. Pendiente, Aprobado, Rechazado).|
|createdAt|timestamp|Private|Fecha y hora en que se creó el registro de verificación.|
|updatedAt|timestamp|Private|Fecha y hora de la última actualización del registro.|
|verificationAttemptLogs|list|Private|Registros de intentos de verificación realizados.|


### 5.2.6. Bounded Context Software Architecture Component Level Diagrams

![](assets/chapter5/2/2_architecture.png)

### 5.2.7. Bounded Context Software Architecture Code Level Diagrams

#### 5.2.7.1. Bounded Context Domain Layer Class Diagrams

![](assets/chapter5/2/2_class.png)

#### 5.2.7.2. Bounded Context Database Design Diagram

![](assets/chapter5/2/2_database.png)


## 5.3. Bounded Context: Service Access Management

### 5.3.1. Domain Layer

Aggregate 

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|ServiceAccess|Core Aggregate|Gestiona y controla el acceso a los servicios, vinculando a los perfiles con los permisos necesarios para acceder a servicios específicos.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|profileId|Integer|Private|Identificador único del perfil asociado a este acceso de servicio.|
|serviceId|Integer|Private|Identificador único del servicio al que se está gestionando el acceso.|
|accessLevel|String|Private|Nivel de acceso concedido al perfil (e.g., "read-only", "full access").|
|accessStatus|String|Private|Estado actual del acceso (e.g., "granted", "revoked", "pending").|
|grantedAt|Timestamp|Private|Fecha y hora en que se concedió el acceso al servicio.|
|revokedAt|Timestamp|Private|Fecha y hora en que se revocó el acceso, si es aplicable.|

Methods

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|grantAccess|void|Public|Concede acceso al perfil para un servicio determinado, ajustando el accessLevel y el accessStatus.|
|revokeAccess|void|Public|Revoca el acceso del perfil al servicio especificado, actualizando el accessStatus a "revoked" y registrando la fecha en revokedAt.|
|updateAccessLevel|void|Public|Actualiza el nivel de acceso del perfil a un servicio específico (e.g., cambiar de "read-only" a "full access").|
|checkAccessStatus|String|Public|Devuelve el estado actual del acceso de un perfil a un servicio específico (e.g., "granted", "revoked").|
|logAccessAttempt|void|Private|Registra un intento de acceso al servicio, independientemente de si fue exitoso o no, con detalles adicionales para auditoría.|

### 5.3.2. Interface Layer

Controller

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|ServiceAccessController|REST API|Controla las solicitudes relacionadas con la gestión del acceso a los servicios, sirviendo como interfaz entre los usuarios y el sistema.|

Methods

|**Name**|**Return Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|grantAccess|HTTP Response|Public|Recibe una solicitud para conceder acceso a un servicio determinado para un perfil específico.|
|revokeAccess|HTTP Response|Public|Recibe una solicitud para revocar el acceso de un perfil a un servicio específico.|
|updateAccessLevel|HTTP Response|Public|Permite modificar el nivel de acceso de un perfil a un servicio determinado, ajustando permisos como sea necesario.|
|checkAccessStatus|JSON|Public|Devuelve el estado actual del acceso de un perfil a un servicio, indicando si el acceso está concedido o revocado.|
|logAccessAttempt|HTTP Response|Private|Registra y notifica los intentos de acceso al sistema, utilizado internamente para auditoría y monitoreo.|


### 5.3.3. Application Layer

Handler

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|ServiceAccessHandler|Command Handler|Gestiona las operaciones relacionadas con la concesión, revocación y actualización del acceso a los servicios.|
|AccessAuditHandler|Event Handler|Se encarga de manejar los eventos relacionados con los intentos de acceso, registrándolos en el sistema para auditoría.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|serviceId|UUID|Private|Identificador único del servicio para el cual se está gestionando el acceso.|
|profileId|UUID|Private|Identificador único del perfil que solicita o tiene acceso a un servicio.|
|accessLevel|String|Private|Define el nivel de acceso otorgado (por ejemplo, "lectura", "escritura", "administrador").|
|requestTimestamp|Timestamp|Private|Almacena la fecha y hora de la solicitud de acceso o revocación, utilizado para fines de auditoría.|
|accessStatus|Boolean|Private|Indica si el acceso fue concedido (true) o revocado (false).|


### 5.3.4. Infrastructure Layer

Repository

|**Name**|**Category**|**Purpose**|
| :- | :- | :- |
|ServiceAccessRepository|Data Repository|Almacena y recupera la información relacionada con los accesos a servicios. Mantiene el estado del acceso concedido o revocado para los perfiles.|
|AccessAuditRepository|Event Repository|Almacena eventos relacionados con auditorías de accesos para su posterior análisis o seguimiento.|

Attributes

|**Name**|**Data Type**|**Visibility**|**Description**|
| :- | :- | :- | :- |
|serviceAccessId|UUID|Private|Identificador único del acceso al servicio, utilizado para la gestión y referencia de accesos.|
|profileId|UUID|Private|Identificador único del perfil que posee o solicita acceso al servicio.|
|accessLevel|String|Private|Indica el nivel de acceso otorgado (por ejemplo, "lectura", "escritura", "administrador").|
|accessTimestamp|Timestamp|Private|Fecha y hora de la acción de otorgar o revocar acceso, útil para auditoría y seguimiento.|
|auditEventId|UUID|Private|Identificador único para eventos de auditoría, usado para rastrear acciones relacionadas con el acceso a servicios.|


### 5.3.6. Bounded Context Software Architecture Component Level Diagrams

![](assets/chapter5/3/3_architecture.png)

### 5.3.7. Bounded Context Software Architecture Code Level Diagrams

#### 5.3.7.1. Bounded Context Domain Layer Class Diagrams

![](assets/chapter5/3/3_class.png)

#### 5.3.7.2. Bounded Context Database Design Diagram

![](assets/chapter5/3/3_database.png)

## 5.X. Bounded Context: <Bounded Context Name>

### 5.X.1. Domain Layer

### 5.X.2. Interface Layer

### 5.X.3. Application Layer

### 5.X.4. Infrastructure Layer

### 5.X.6. Bounded Context Software Architecture Component Level Diagrams

### 5.X.7. Bounded Context Software Architecture Code Level Diagrams

#### 5.X.7.1. Bounded Context Domain Layer Class Diagrams

#### 5.X.7.2. Bounded Context Database Design Diagram