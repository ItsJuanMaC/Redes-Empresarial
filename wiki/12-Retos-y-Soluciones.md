# 12. Retos y soluciones por capa TCP/IP

Estos son los problemas que aparecieron durante el montaje y la configuración, clasificados según la capa del modelo TCP/IP en la que ocurrieron.

## Capa de acceso a red

| Problema | Causa | Solución |
| --- | --- | --- |
| El WIC-2T no se insertaba | El 2811 estaba encendido | Apagar el router en Physical, insertar el módulo y volver a encender |
| El 3650 no encendía | Viene sin fuente de poder | Agregar la AC-POWER-SUPPLY |
| Los puertos seriales no coincidían con el plan | Los WIC quedaron en las ranuras 2 y 3 | Usar S0/2/x y S0/3/x, y confirmar el mapa con `show cdp neighbors` |
| PT rechazó `interface range` en los seriales | Limitación del IOS de Packet Tracer | Configurar cada interfaz por separado |

## Capa de Internet

| Problema | Causa | Solución |
| --- | --- | --- |
| El túnel GRE no llevaba IPv6 | Comportamiento de PT con `tunnel mode gre ip` | Usar `tunnel mode ipv6ip` (6in4) [2] |
| El tráfico se cortó al activar IPsec | La ACL crypto con `permit gre` no coincidía con el 6in4 | Usar `permit ip host 86.106.78.22 host 86.106.78.26` |
| Las redes de Madrid no aparecían en R1_BOG | El 3650 no anunciaba sus SVIs por OSPFv3 | Estática a EB22::/48 en R2_ESP con `redistribute static`, y ruta por defecto en el MLSW |
| No había ruta IPv4 de gestión entre sedes | La INTERNET no conoce las redes privadas | Tunnel1 GRE (10.255.255.0/30) con rutas estáticas |
| Riesgo de bucles por la redistribución mutua | Hay dos puntos de redistribución | Las distancias administrativas (90 / 110 / 170) favorecen siempre la ruta nativa |

## Capa de transporte

| Problema | Causa | Solución |
| --- | --- | --- |
| El Tracker se quedaba sin conexión | Un programa arrancaba antes que su servidor | Reconexión automática si no llega el ACK en 15 s |
| El primer GET SNMP no respondía | ARP todavía se estaba resolviendo | Repetir el GET |
| Las ACLs podían cortar otros servicios | El deny implícito al final de toda ACL | Terminar cada ACL con `permit ipv6 any any` |

## Capa de aplicación

| Problema | Causa | Solución |
| --- | --- | --- |
| «Host Name Unresolved» en los PCs dual-stack | El navegador de PT usa el DNS IPv4 si el PC tiene IPv4 | IPv4 10.12.100.11 en el DNS, configurada también como DNS de los PCs internos |
| PT rechazó `snmp-server community X RO 10` | No acepta una ACL ligada a la comunidad | Comunidades sin ACL; el filtro queda en el direccionamiento y la ACL GUEST_BOG |
| SNMP v1 agotaba el tiempo | Versión del agente | Usar v2 en el MIB Browser |
| El MLSW 3650 no responde SNMP | Limitación de PT | Se documentó; se gestionan los routers y los 2960 |
| No fue posible la vista web del Dashboard (bonus) | Los PCs de PT no tienen servidor HTTP en Programming | Las alertas se muestran en la consola de PC7 y viajan en el ACK |

## Limitaciones que quedan

- **SNMP en MLSW_MAD:** no responde al MIB Browser aunque tiene las comunidades configuradas (captura 29).
- **Vista web del Dashboard:** no se implementó.
- **SNMP por IPv6:** la gestión se hace por IPv4 privado (servicio adicional) y no por IPv6.
