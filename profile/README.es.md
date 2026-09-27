# <div align="center">

# Senda

Envía lo que importa. En segundos, estés donde estés.

Senda es un agente de IA conversacional —disponible en español e inglés a través de un sencillo chat de WhatsApp y respaldado por Stellar USDC— que no requiere experiencia previa en criptomonedas. Permite a cualquier persona en Argentina recibir, mover y generar rendimientos en dólares digitales sin salir nunca del chat.

## ¿Qué lo hace diferente?

Casi todas las billeteras de *stablecoins* diseñadas para mercados emergentes exigen una de dos
concesiones: ceder el control de los fondos a la empresa que opera la aplicación, o
gestionar la conversión a moneda local mediante una integración cerrada y propietaria con un único proveedor,
lo que deja al usuario sin visibilidad sobre qué sucede con su dinero mientras está en tránsito. Senda elimina ambos problemas. La billetera del usuario está integrada y es de autocustodia: el usuario es el verdadero propietario criptográfico desde el primer mensaje, no simplemente un cliente de un custodio. La conversión ARS↔USDC se ejecuta sobre SEP-24 —el protocolo abierto y estandarizado de Stellar para depósitos y retiros gestionados—, ofreciendo estados de transacción legibles que el agente de IA explica al usuario en tiempo real, en lugar de dejarlo esperando una respuesta de soporte.

| | Senda | La mayoría de las billeteras de *stablecoins* basadas en chat |
|---|---|---|
| **Custodia** | Una cuenta Stellar por persona, integrada mediante Privy. Senda no almacena la frase semilla; firma utilizando una clave de sesión delegada por el usuario durante el registro. | La empresa controla las claves; custodia centralizada |
| **Liquidación en moneda fiat** | Protocolo abierto (SEP-24) a través de un *anchor* regulado | API cerrada y propietaria de un único proveedor |
| **Salida a moneda fiat en Argentina** | Directo al CVU de Mercado Pago del usuario | A menudo sin solución |
| **Rendimiento** | Blend v2, préstamos en Soroban. En Senda, la posición *on-chain* pertenece a la tesorería, mientras que la participación de cada individuo se registra dentro de Senda. Los fondos pueden retirarse. | Producto financiero propietario; el motor de rendimiento carece de transparencia |
| **Cobros** | Enlace SEP-7. El pago en USDC es directo. Una vez enviado, la liberación de los fondos no puede quedar sujeta a condiciones. | Pago directo e irreversible. |
| **Privacidad** | Hoja de ruta activa hacia Tokens Confidenciales / Pagos Privados en Stellar | Historial de transacciones y saldos expuestos por defecto |

## Estado actual

Senda se encuentra en fase de desarrollo activo en la red de pruebas (Testnet) de Stellar. En el repositorio `senda-backend`, el flujo de trabajo de WhatsApp ya es funcional a nivel de código: mensajes de texto y notas de voz, consulta de saldos, transferencias de USDC, solicitudes de pago SEP-7, registro inicial en la billetera (*onboarding*) y ahorros en Blend. El puente SEP-24 apunta al *anchor* de pruebas `testanchor.stellar.org`: el bot se autentica mediante SEP-10, inicia el flujo del *anchor* y proporciona actualizaciones de estado a través de WhatsApp. No existe un CVU (cuenta virtual) de Mercado Pago vinculado. Alfred Pay y Ripio Ramps aparecen como candidatos en el código, no como clientes activos. Blend v2 está integrado en la red de pruebas: la tesorería deposita fondos en el *pool* y la participación de cada persona se registra en Senda. Cuando se recibe un pago, el bot ofrece la opción de reservar una parte de los fondos. El siguiente hito identificado en los repositorios —que aún no se ha desarrollado— es un programa piloto que incluya una salida a pesos en el mundo real.

## Repositorios

**[`senda-backend`](#)** El producto —bot de WhatsApp (Cloud API v22), registro web (`web-setup`) e integraciones con Stellar— desarrollado en TypeScript. Este repositorio gestiona SEP-7 para cobros, SEP-10 para autenticación con el *anchor*, SEP-24 para retiros, USDC mediante el contrato de activos de Stellar e integración de rendimientos de Blend v2. **[`senda.app`](#)** es el *frontend*.

## Enlaces

- Aplicación en vivo: `[COMPLETAR: URL real o enlace de WhatsApp del bot — wa.me/...]`
- Documentación: `[COMPLETAR: URL real, si corresponde]`
