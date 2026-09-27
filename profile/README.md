# <div align="center">

#  Senda

Envía lo que importa. En segundos, estés donde estés.

Senda es un agente de IA conversacional en español y Ingles a través de un simple chat de WhatsApp,impulsado por Stellar USDC, sin necesidad de experiencia en criptomonedas, Permite a cualquier persona en Argentina cobrar, mover y hacer rendir dólares digitales sin salir del chat.

## ¿Qué hace que esto sea diferente?

Casi todas las wallets de stablecoins pensadas para mercados emergentes piden una de dos
concesiones: entregarle el control de tus fondos a la empresa que opera la app, o resolver la
conversión a moneda local mediante una integración propietaria y cerrada de un solo proveedor, sin
visibilidad de qué pasa con tu plata mientras se mueve. Senda elimina las dos. La wallet del
usuario es embebida y self-custodial — el usuario es el owner criptográfico real desde el primer
mensaje, no un cliente de un custodio. La conversión ARS↔USDC corre sobre SEP-24, el protocolo
abierto y estandarizado de Stellar para depósito y retiro alojado, con estados de transacción
legibles que el propio agente de IA le explica al usuario en tiempo real, en vez de dejarlo
esperando una respuesta de soporte.

| | Senda | La mayoría de wallets de stablecoins por chat |
|---|---|---|
| **Custodia** | Cuenta Stellar por persona, embebida con Privy. Senda no guarda la seed. Firma un session signer que el usuario delegó en el alta. | La empresa controla las claves, custodia centralizada |
| **Liquidación fiat** | Protocolo abierto (SEP-24) contra un anchor regulado | API propietaria y cerrada de un solo proveedor |
| **Salida a fiat en Argentina** | Directo al CVU de Mercado Pago del usuario | Muchas veces no está resuelto. |
| **Rendimiento** | Blend v2, lending en Soroban. En Senda la posición on-chain es de la tesorería y la parte de cada uno se anota en Senda. Se puede sacar. | Producto financiero propio, sin transparencia del motor de yield |
| **Cobros** | Link SEP-7. El pago de USDC es directo. Si sale, no hay cómo condicionar la liberación. | Pago directo e irreversible. |
| **Privacidad** | Roadmap activo hacia Confidential Tokens / Stellar Private Payments | Historial de montos y balances expuesto por defecto |

## Dónde están las cosas

Senda está en desarrollo activo sobre Stellar Testnet. En senda-backend el flujo de WhatsApp ya corre en código: texto y nota de voz, saldo, envío de USDC, cobro con link SEP-7, alta de wallet y ahorro en Blend. El puente SEP-24 apunta al ancla de prueba testanchor.stellar.org: el bot autentica con SEP-10, abre el flujo del ancla y avisa cada estado por WhatsApp. No hay un CVU de Mercado Pago acreditado. Alfred Pay y Ripio Ramps figuran como candidatos, no como clientes en el código. Blend v2 está integrado en testnet: la tesorería deposita en el pool y la parte de cada persona se anota en Senda. Cuando entra un cobro, el bot ofrece apartar una parte. El próximo hito que los propios repos marcan, y que todavía no está construido, es un piloto con salida real a pesos. 

## Repositorios

**[`senda-backend`](#)** Producto.bot de WhatsApp (Cloud API v22), el alta web en web-setup y las integraciones de Stellar, en TypeScript. Ahí están SEP-7 para los cobros, SEP-10 para autenticarse contra el ancla, SEP-24 para el retiro, USDC por el Stellar Asset Contract, y el yield de Blend v2.

**[`senda.app`](#)** es el frontend

## Enlaces

- App en vivo: `[COMPLETAR: URL real, o link de WhatsApp del bot — wa.me/...]`
- Documentación: `[COMPLETAR: URL real, si existe]`
