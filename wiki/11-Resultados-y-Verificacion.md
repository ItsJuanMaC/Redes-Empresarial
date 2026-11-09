# 11. Resultados y verificación (Tarea 10)

Se hicieron 37 pruebas, cada una con su captura en la carpeta [`Capturas Proyecto`](https://github.com/ItsJuanMaC/Redes-Empresarial/tree/main/Capturas%20Proyecto) del repositorio. 36 dieron el resultado esperado. La única que no respondió fue el SNMP hacia el MLSW 3650, por una limitación de Packet Tracer (ver [Retos](12-Retos-y-Soluciones)).

En la columna Captura, el número enlaza a la imagen.

| # | Requisito | Prueba | Desde | Resultado | Captura |
| --- | --- | --- | --- | --- | --- |
| 1 | Montaje | Vista lógica de la topología | — | Todos los enlaces en verde | [01](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/01_Topologia_general.jpg) |
| 2 | Enrutamiento | `show ip route` | ISP_BOG | Rutas C, D, O y redistribuidas | [02](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/02_ISP_BOG_show_ip_route.jpg) |
| 3 | Enrutamiento | Vecinos EIGRP, OSPF y CDP | ISP_BOG | Adyacencias establecidas | [03](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/03_ISP_BOG_vecinos_EIGRP_OSPF_CDP.jpg) |
| 4 | Redistribución | Tabla de rutas y protocolos | ISP_FL | Rutas EIGRP como O E2 | [04](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/04_ISP_FL_rutas_y_protocolos.jpg) |
| 5 | Túnel | IPv6 int brief, ISAKMP, OSPFv3 | R1_BOG | Tunnel0 up, QM_IDLE, vecino FULL | [05](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/05_R1_BOG_IPv6_ISAKMP_OSPFv3.jpg) |
| 6 | IPsec | `show crypto ipsec sa` | R1_BOG | encaps/decaps > 0 | [06](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/06_R1_BOG_show_crypto_ipsec_sa.jpg) |
| 7 | Túnel y ACL | Rutas OSPFv3, ACL, ping a MAD | R1_BOG | Rutas EB22 por Tunnel0, ping OK | [07](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/07_R1_BOG_rutas_OSPFv3_ACL_ping_MAD.jpg) |
| 8 | VLANs | `show vlan brief`, `show int trunk` | SW2 | VLANs 20/30/40/99, nativa 99 | [08](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/08_SW2_VLAN_y_troncales.jpg) |
| 9 | DHCPv6 | `ipconfig /all` | PC1 | IPv6 EA12:20::, DNS ::11, jaz.net | [09](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/09_PC1_ipconfig_DHCPv6.jpg) |
| 10 | DNS | Registros del servidor | DNS Server | AAAA de jaz.net y www.jaz.net | [10](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/10_DNS_Server_registros_AAAA.jpg) |
| 11 | ACL BOG | http://jaz.net | PC1 (Guest) | Abre | [11](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/11_PC1_invitado_HTTP_OK.jpg) |
| 12 | ACL BOG | https://jaz.net | PC1 (Guest) | Bloqueado | [12](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/12_PC1_invitado_HTTPS_bloqueado.jpg) |
| 13 | ACL BOG | https://jaz.net | PC2 (Internal) | Abre | [13](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/13_PC2_interno_HTTPS_OK.jpg) |
| 14 | ACL BOG | http://jaz.net | PC2 (Internal) | Bloqueado | [14](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/14_PC2_interno_HTTP_bloqueado.jpg) |
| 15 | ACL MAD | https://jaz.net | PC7 (Internal) | Abre | [15](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/15_PC7_interno_HTTPS_OK.jpg) |
| 16 | ACL MAD | http://jaz.net | PC7 (Internal) | Bloqueado | [16](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/16_PC7_interno_HTTP_bloqueado.jpg) |
| 17 | ACL MAD | http://jaz.net | PC5 (Guest) | Abre | [17](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/17_PC5_invitado_HTTP_OK.jpg) |
| 18 | ACL MAD | https://jaz.net | PC8 (Guest) | Bloqueado | [18](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/18_PC8_invitado_HTTPS_bloqueado.jpg) |
| 19 | ACL MAD | https://jaz.net | PC6 (Internal) | Abre | [19](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/19_PC6_interno_HTTPS_OK.jpg) |
| 20 | ACL BOG | http://jaz.net | PC3 (Guest) | Abre | [20](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/20_PC3_invitado_HTTP_OK.jpg) |
| 21 | ACL MAD | `show ipv6 access-list` y rutas | R2_ESP | Coincidencias en FILTRO_MAD | [21](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/21_R2_ESP_ACL_y_rutas_IPv6.jpg) |
| 22 | Conectividad | Ping a impresoras | PCs | Respuestas OK | [22](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/22_Ping_impresoras_BOG_y_MAD.jpg) |
| 23 | SNMP | GET | PC2 → SW2 | Devuelve sysName | [23](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/23_SNMP_GET_PC2_a_SW2.jpg) |
| 24 | SNMP | SET | PC2 → SW2 | Valor cambiado | [24](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/24_SNMP_SET_PC2_a_SW2.jpg) |
| 25 | SNMP | GET | PC2 → R1_BOG | OK | [25](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/25_SNMP_GET_PC2_a_R1_BOG.jpg) |
| 26 | SNMP | GET | PC7 → SW5 | OK | [26](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/26_SNMP_GET_PC7_a_SW5.jpg) |
| 27 | SNMP | GET | PC7 → R2_ESP | OK | [27](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/27_SNMP_GET_PC7_a_R2_ESP.jpg) |
| 28 | SNMP | GET (prueba negativa) | PC8 (Guest) | Timeout esperado | [28](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/28_SNMP_invitado_PC8_rechazado.jpg) |
| 29 | SNMP | GET | PC7 → MLSW | Timeout (limitación de PT) | [29](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/29_SNMP_MLSW_sin_respuesta.jpg) |
| 30 | Tracker | Consola de la App | PC4 | Envía y recibe ACK-RELAY | [30](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/30_Tracker_App_PC4.jpg) |
| 31 | Tracker | Consola del Relay | Tracker Server | Recibe y reenvía a PC7 | [31](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/31_Tracker_Relay_Server.jpg) |
| 32 | Tracker | Consola del Dashboard | PC7 | ALERTA ZONA y ALERTA ACTIVIDAD | [32](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/32_Tracker_Dashboard_PC7_alertas.jpg) |
| 33 | Tracker | Simulación TCP | PC4 → Tracker Server | Segmento al puerto 5000 | [33](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/33_Simulacion_TCP_PC4_a_TrackerSrv.jpg) |
| 34 | Tracker | Simulación TCP | Relay → PC7 | Cruza el túnel cifrado | [34](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/34_Simulacion_TCP_Relay_a_PC7.jpg) |
| 35 | Tracker | Simulación TCP | PC7 → Relay | ACK de vuelta | [35](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/35_Simulacion_TCP_ACK_de_vuelta.jpg) |
| 36 | SNMP | Simulación SNMP | PC2 | GetRequest | [36](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/36_Simulacion_SNMP_peticion_PC2.jpg) |
| 37 | SNMP | Simulación SNMP | Agente → PC2 | GetResponse | [37](https://raw.githubusercontent.com/ItsJuanMaC/Redes-Empresarial/main/Capturas%20Proyecto/37_Simulacion_SNMP_respuesta_PC2.jpg) |

## Exportación de configuraciones

1. En cada router y switch se guardó la configuración con `copy running-config startup-config`.
2. Desde Packet Tracer se exportó la configuración de cada equipo a un `.txt`.
3. El `.pkt` final contiene el `main.py` de los tres programas del Tracker.

## Cómo repetir las pruebas

- **CLI:** contraseña `cisco`, enable `class`.
- **Web:** Desktop → Web Browser, abrir `http://jaz.net` y `https://jaz.net`.
- **SNMP:** MIB Browser → Advanced, comunidades `jazRO`/`jazRW`, versión v2. Si la primera petición agota el tiempo, presionar GO otra vez.
- **Tracker:** Programming → Run, primero en PC7, luego en Tracker Server y al final en PC4. Las alertas salen en PC7 a los 60 s aproximadamente.
