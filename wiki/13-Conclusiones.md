# 13. Conclusiones y recomendaciones

## Conclusiones

- Un túnel 6in4 une dos intranets IPv6 a través de una INTERNET que solo maneja IPv4, sin tocar los ISP [2]. Con IPsec en los dos routers de borde basta para que en la INTERNET solo se vea tráfico ESP [3].
- La redistribución mutua EIGRP–OSPF en dos puntos funciona y da conectividad completa. Las distancias administrativas evitan que una ruta redistribuida reemplace a una nativa.
- Router-on-a-stick y las SVIs en un switch multicapa resuelven el mismo problema. La diferencia está en el costo y en dónde se concentra el tráfico entre VLANs.
- Las ACLs IPv6 extendidas, aplicadas de entrada y cerca del origen, separan a los invitados (solo HTTP) de los internos (solo HTTPS). Siempre deben cerrar con `permit ipv6 any any`, o cortan DNS, ICMPv6 y el enrutamiento.
- SNMPv2c viaja en texto claro [8]. Por eso conviene limitarlo a la VLAN Internal y hacerlo cruzar entre sedes solo por el túnel cifrado.
- El Employee Tracker muestra un flujo TCP de aplicación que atraviesa VLANs, la DMZ, el túnel e IPsec de extremo a extremo. El ACK de aplicación y la reconexión automática lo hacen robusto frente al orden de arranque.

## Recomendaciones

1. Hacer la prueba previa con el MIB Browser y los sockets IPv6 antes de montar toda la red. Así se anticipa la necesidad de dual-stack para la gestión.
2. Guardar el `.pkt` con un nombre nuevo al terminar cada etapa.
3. En una red real, usar SNMPv3, que agrega autenticación y cifrado, en lugar de v2c.
4. Llevar la tabla de puertos actualizada mientras se cablea, porque los puertos reales pueden no coincidir con el plan.
