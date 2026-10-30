# Drinks on Chain

**Trazabilidad verificable y tokenización de vinos y singanis bolivianos sobre la red Stellar.**

Drinks on Chain permite a bodegas y destilerías de Bolivia registrar cada lote **de la parcela a la botella**, publicar un **pasaporte digital** que se verifica escaneando el QR de la etiqueta, y representar cada botella con un **NFT** en la red Stellar.

> Este repositorio muestra el **estado actual de la implementación**. El código vive en los repositorios enlazados abajo, y este documento se actualiza a medida que se implementa algo nuevo en ellos.
>
> Última actualización: **30 de octubre de 2026**.

---

## Estado actual

| Componente | Qué hace hoy | Estado |
|---|---|---|
| Plataforma base | Cuentas y roles por organización, doble factor para el equipo interno, bitácora inmutable encadenada por huellas, integración continua | ✅ Implementada |
| Alta de bodegas | Solicitud y aprobación de bodegas, activación con prefijo de lote propio, invitación del equipo con roles | ✅ Implementada |
| ERP de trazabilidad | Registro completo del lote (parcela, cosecha, dictamen, fermentación, crianza o destilación y reposo, embotellado, laboratorio) con reglas de Denominación de Origen que no se pueden saltar, un código único por botella y expediente con huella criptográfica | ✅ Implementado y conectado al backend |
| Pasaporte público | Consulta pública del lote o de cada botella por su código, con prueba de que la botella pertenece a un expediente cerrado | ✅ Implementado en el backend |
| Contrato inteligente | NFT por botella, un contrato por bodega; emitir, entregar y quemar | ✅ Desplegado en la red de pruebas de Stellar |
| Tokenización | Cuenta y contrato de cada bodega en la red, emisión de NFT, anclaje de la huella del expediente en la red, conciliación entre base de datos y red | 🟡 Implementada y probada en una red Stellar local; en integración |
| Sitio de bodegas | Mapa interactivo de los valles de Tarija y Cinti y presentación de la red | ✅ En línea |

---

## Repositorios

| Componente | Repositorio | Tecnología |
|---|---|---|
| **Backend (API y procesos)** | [drinks-on-chain-back](https://github.com/drinks-on-chain/drinks-on-chain-back) | Node.js, NestJS, TypeScript, PostgreSQL, Redis |
| **ERP de trazabilidad** | [drinks-on-chain-erp](https://github.com/drinks-on-chain/drinks-on-chain-erp) | Next.js, React, TypeScript |
| **Contratos inteligentes** | [drinks-on-chain-contracts](https://github.com/drinks-on-chain/drinks-on-chain-contracts) | Rust, Soroban (Stellar), OpenZeppelin Stellar Contracts |
| **Sitio de bodegas** | [drinks-on-chain-front](https://github.com/drinks-on-chain/drinks-on-chain-front) | Next.js, React Three Fiber (WebGL) |

---

## Evidencias verificables

| Evidencia | Enlace |
|---|---|
| Contrato de la bodega de demostración "Altos de Calamuchita" en la red de pruebas de Stellar | [stellar.expert](https://stellar.expert/explorer/testnet/contract/CDUUCPA5JQVDP6EEI3CWT5MS4SGEPD2WS2SN6XSZCGPATTJSO2SZQS6M) |
| Contrato de la destilería de demostración "Cinti Viejo" | [stellar.expert](https://stellar.expert/explorer/testnet/contract/CC5M35BGIVRDZ5HEXMORAFO2D6RGOARJ7MLOGU56JCX5J5C66HFJKDFF) |
| Costes reales medidos en la red (emitir, entregar, quemar) | [costes.md](https://github.com/drinks-on-chain/drinks-on-chain-contracts/blob/main/docs/costes.md) |
| Sitio de bodegas en línea | [drinks-on-chain-bodegas.vercel.app](https://drinks-on-chain-bodegas.vercel.app) |
| ERP en línea (acceso de demostración bajo solicitud) | [drinks-on-chain-erp.vercel.app](https://drinks-on-chain-erp.vercel.app) |

---

## Más información

| Documento | Contenido |
|---|---|
| [docs/01-producto.md](docs/01-producto.md) | Problema, solución, usuarios y ciclo de vida de una botella |
| [avances/](avances/) | Registro de lo implementado, por fecha |
