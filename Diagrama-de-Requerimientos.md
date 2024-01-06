```mermaid
requirementDiagram

    requirement sistema_gestion_hospitalaria {
    id: 1
    text: Sistema de Gestión Hospitalaria debe proporcionar funcionalidades esenciales para la gestión de pacientes y empleados.
    risk: high
    verifymethod: test
    }

    functionalRequirement gestion_pacientes {
    id: 1.1
    text: El sistema debe permitir el registro, actualización y consulta de datos de pacientes.
    risk: medium
    verifymethod: inspection
    }

    functionalRequirement gestion_empleados {
    id: 1.2
    text: El sistema debe permitir la gestión de empleados, incluyendo doctores, enfermeros y personal administrativo.
    risk: medium
    verifymethod: demonstration
    }

    performanceRequirement rendimiento {
    id: 1.3
    text: El sistema debe responder en menos de 2 segundos para las operaciones comunes.
    risk: medium
    verifymethod: test
    }

    interfaceRequirement interfaz_usuario {
    id: 1.3.1
    text: La interfaz de usuario debe ser intuitiva y adaptarse a dispositivos móviles y de escritorio.
    risk: low
    verifymethod: inspection
    }

    designConstraint seguridad {
    id: 1.3.2
    text: Todas las transacciones y datos deben ser seguros y cumplir con las regulaciones de privacidad.
    risk: high
    verifymethod: analysis
    }

    element doc_especificaciones {
    type: "documento"
    docRef: reqs/sistema_gestion_hospitalaria_espec
    }

    element suite_pruebas {
    type: "test suite"
    docRef: github.com/suite_pruebas_gestion_hospitalaria
    }

    element mockup_ui {
    type: "prototipo"
    docRef: design/mockup_ui
    }

    mockup_ui - satisfies -> interfaz_usuario
    sistema_gestion_hospitalaria - contains -> gestion_pacientes
    sistema_gestion_hospitalaria - contains -> gestion_empleados
    gestion_empleados - derives -> rendimiento
    gestion_pacientes - refines -> seguridad
    suite_pruebas - verifies -> rendimiento
    sistema_gestion_hospitalaria <- copies - doc_especificaciones

```