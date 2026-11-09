# 16. Uso de IA

El enunciado exige declarar el uso de inteligencia artificial.

## Herramienta

**Claude** (Anthropic).

## Para qué se usó

1. **Guía de trabajo:** a partir del enunciado y la rúbrica, se generó una guía de Packet Tracer con el plan de direccionamiento, los comandos de cada tarea y la lista de verificación.
2. **Diseño:** el plan de direccionamiento con X = 2, las VLANs y las configuraciones base de cada equipo.
3. **Configuración:** con la herramienta de control del computador, Claude aplicó las configuraciones en el Packet Tracer del estudiante. También escribió los tres programas Python del Employee Tracker.
4. **Verificación:** ejecutó las 37 pruebas y tomó las capturas.
5. **Documentación:** redactó el documento compilado del proyecto y esta Wiki.

## Instrucciones dadas a la IA (resumen)

- «Mira el documento y dime cómo realizarías la actividad en Packet Tracer» (con el enunciado y la rúbrica adjuntos).
- «El número de mi equipo es el 2, el dominio debería ser JAZ.net.»
- «Tengo abierto Packet Tracer, utiliza mi PC para realizar todo.»
- «Termina los pendientes de Packet Tracer.»
- «Verifica todo y realiza un documento donde describas todo lo que hiciste; al realizar las pruebas toma una captura de pantalla.»
- «Conéctate con mi repo y elabora la Wiki.»

## Cómo se validaron las respuestas

- Cada comando se ejecutó en Packet Tracer 9.0.1. Lo que PT rechazó o no funcionó se corrigió, y esas correcciones están documentadas en [Túnel IPv6 e IPsec](06-Tunel-IPv6-e-IPsec), [SNMP](09-SNMP) y [Retos y soluciones](12-Retos-y-Soluciones). Algunos ejemplos:
  - el túnel pasó de GRE a 6in4;
  - se cambió la ACL de crypto;
  - las comunidades SNMP quedaron sin ACL;
  - se le dio IPv4 al DNS;
  - se agregaron estáticas porque el MLSW no anunciaba sus SVIs por OSPFv3.
- La red funciona según las [37 capturas](11-Resultados-y-Verificacion), tomadas sobre la topología final.
- Las referencias son RFC públicos que el equipo puede consultar directamente.

> El equipo es responsable de revisar y entender cada configuración antes de la sustentación.
