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

| Driver ID | Título de Driver  | Blockchain | Microservicios | Cliente-Servidor Tradicional |
|-----------|----------|--------|---------|------------|
|ADB-01|Seguridad y Protección de Datos|**PROS:** Alta seguridad, inmutabilidad, cifrado end-to-end. **CONTRA:** Complejidad en la implementación y en el cumplimiento regulatorio.|**PROS:** Modularidad, ya que cada servicio maneja su propia seguridad.**CONTRA:** Requiere una alta coordinación entre servicios para mantener seguridad global.|**PRO:** Sencillez en la implementación de medidas de seguridad. **CONTRA:** Menor robustez ante ataques o compromisos de un servidor.|
|ADB-02|Escalabilidad del Sistema|**PROS:** Escalabilidad casi infinita a medida que crece la red. **CONTRA:** Latencia en las transacciones por la validación distribuida.|**PROS:** Escalabilidad granular, cada servicio puede escalar por separado. **CONTRA:** Puede haber sobrecarga de comunicación y complejidad en la coordinacion.|**PROS:** Sencillo de gestionar en pequeñas escalas. **CONTRA:** Difícil escalar para manejar grandes volúmenes de usuarios o transacciones.|
|ADB-03|Sincronización de Datos Offline|**PROS:** Inmutabilidad y consistencia aseguradas cuando se sincronizan los datos. **CONTRA:** Complejidad en la implementación de mecanismos de sincronización offline.|**PROS:** Flexibilidad en la implementación de sincronización. **CONTRA:** Puede generar inconsistencias si los servicios no están bien coordinados.|**PROS:** Fácil de implementar la sincronización local.**CONTRA:**La lógica de sincronización es menos robusta y difícil de manejar en escenarios de desconexión prolongada.|
|ADB-04|Integración con Sistemas Gubernamentales|**PROS:** Provee trazabilidad y transparencia completa a las autoridades. **CONTRA:** Dificultades para que las instituciones adopten la tecnología blockchain.|**PROS:** Integración ágil con sistemas externos mediante APIs. **CONTRA:** La coordinacion de muchos servicios puede complicar la integración en tiempo real.|**PROS:** Fácil implementación inicial con sistemas externos.**CONTRA:**Menor flexibilidad y escalabilidad en la integración a gran escala.|

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