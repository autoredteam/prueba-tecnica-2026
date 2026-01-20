# Sistema de Gestión de Contratos de Vehículos

## Contexto del Problema

La empresa gestiona **contratos de compra y venta de vehículos**. Necesitamos diseñar un sistema que permita crear, gestionar y hacer seguimiento de estos contratos a lo largo de todo su ciclo de vida.

## ¿Qué es un Contrato?

Un contrato es un documento que:

- **Contiene información de un vehículo** (datos del vehículo involucrado en la transacción)
- **Tiene uno o más firmantes** (las personas que deben firmar el contrato)
- **Debe ser firmado por todos** los firmantes para considerarse completo
- **Puede ser notarizado** por un notario (opcional, pero requiere que esté firmado primero)
- **Debe enviarse por email** al cliente una vez completado

## Estados del Contrato

El contrato puede encontrarse en uno de los siguientes estados:

- **CREATED**: El contrato ha sido creado pero aún no está listo para ser firmado
- **PENDING_SIGNATURE**: El contrato está pendiente de ser firmado por uno o más firmantes
- **SIGNED**: Todos los firmantes han completado su firma
- **NOTARIZED**: El contrato ha sido notarizado por un notario

## Reglas de Negocio

El sistema debe cumplir con las siguientes reglas:

1. **No se puede notarizar si no está firmado**: Un contrato solo puede pasar al estado `NOTARIZED` si previamente está en estado `SIGNED`

2. **Un firmante firma una sola vez por contrato**: Cada firmante solo puede firmar una vez en un contrato específico. No se permiten firmas duplicadas

3. **Un firmante puede participar en multiples transacciones**: Un firmante puede firmar muchos contratos de distintios vehiculos.

4. **Un vehículo solo puede estar en un contrato activo**: Un vehículo no puede estar asociado a múltiples contratos activos simultáneamente

## Stack de Referencia

Para el diseño del sistema, considera que estas trabajando con un stack de tecnologías como:

- **Frontend**: Next.js, React
- **Backend**: Node.js, Express
- **Base de datos**: PostgreSQL
- **ORM**: Sequelize

## Metodología de Trabajo

**No es necesario codificar**. El objetivo es **diseñar y plantear soluciones** utilizando herramientas de diseño como:

- **draw.io** (o herramientas similares) para diagramas
- **markdown** para documentar la solución
