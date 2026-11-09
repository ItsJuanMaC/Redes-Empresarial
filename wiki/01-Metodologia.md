# 1. Metodología

El proyecto siguió cuatro fases: **diseño → montaje → configuración → verificación**. Al final de cada fase se guardó el `.pkt` para poder volver atrás si algo se rompía.

## Fases

| Fase | Qué se hizo | Resultado |
| --- | --- | --- |
| Diseño | Lectura del enunciado y la rúbrica, elección de VLANs, protocolos y servicios, subneteo con X = 2 | [Esquema de direccionamiento](02-Direccionamiento) |
| Montaje | Equipos, módulos WIC-2T, fuente del 3650, cableado y nombres según la Figura 1 | [Montaje](03-Montaje-y-Configuracion-Basica) |
| Configuración | Básico → VLANs → enrutamiento INTERNET → túnel + IPsec → OSPFv3 → servicios → ACLs → SNMP → Tracker | Páginas 4 a 10 |
| Verificación | 37 pruebas, cada una con su captura, incluidas capturas en modo Simulación | [Resultados](11-Resultados-y-Verificacion) |

## Prueba previa

Antes de montar toda la red se probaron las dos herramientas de Packet Tracer que pueden no soportar IPv6:

- **Socket TCP del Programming hacia una IPv6:** funciona. El Employee Tracker usa IPv6 de extremo a extremo.
- **MIB Browser hacia una IPv6:** no respondió de forma fiable. Por eso se agregó IPv4 privado (dual-stack) solo en la VLAN Internal, la DMZ y los equipos de red, para la gestión SNMP. Es el **servicio adicional de la Tarea 8**.

## Supuestos de diseño

| Tema | Decisión | Justificación |
| --- | --- | --- |
| MLSW | Cisco 3650-24PS con fuente AC-POWER-SUPPLY | Lo pide el enunciado; en PT viene apagado sin fuente |
| VLAN IDs | 20 Guest, 30 Internal, 40 Server/Printer, 99 Native, iguales en ambas sedes | El enunciado deja «ID ##» libre; cada sede es un dominio L2 separado |
| Miembros | BOG: Guest PC1/PC3, Internal PC2/PC4. MAD: Guest PC5/PC8, Internal PC6/PC7 | Lectura de la figura del enunciado |
| Bloques IPv6 | EA12 LAN BOG, EC12 DMZ y túnel, ED12 loopbacks, EB22 LAN MAD, ED22 enlace R2_ESP–MLSW | Bloques de la figura con X = 2 |
| Inter-VLAN | Router-on-a-stick en BOG; SVIs en el MLSW en MAD | Compara las dos técnicas que pide el curso |
| Enrutamiento IPv6 interno | OSPFv3 proceso 1, área 0 | Estándar abierto [5]; no depende del soporte de EIGRPv6 en el 3650 de PT |
| Migración | Túnel manual 6in4 + IPsec sitio a sitio | Solo toca los routers de borde; los ISP siguen siendo IPv4 [2], [3] |
| EIGRP | AS 2 (número del equipo) | Identifica al equipo |

## Herramientas

- Cisco Packet Tracer 9.0.1 (modos Realtime y Simulation).
- Python de Packet Tracer (Programming) para el Employee Tracker.
- GitHub para el repositorio y esta Wiki.
