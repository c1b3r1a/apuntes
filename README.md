# 4punt3s  :(){ :|:& };:
Apuntes para Hackers, desde las trincheras de Internet con amor.

Ey, antes de meterte al examen, ten claros estos conceptos fundamentales.

Las **4 fases del ciberataque** son tu roadmap:

primero recopilas info (OSINT/footprinting), luego escaneas activamente (fingerprinting con nmap),
explotas vulnerabilidades encontradas
y finalmente haces postexplotación (backdoors, exfiltración, borrar logs).

Una **vulnerabilidad** es un bug o fallo explotable en el sistema, mientras que un **vector de ataque** es el camino que usas para llegar a ella (como un puerto SSH abierto).

La **geolocalización IP** te dice dónde está físicamente un servidor (comandos: curl ipinfo.io, geoiplookup).

Un **sniffer** como Wireshark "huele" paquetes de red en tiempo real, perfecto para ver qué viaja sin cifrar.

**Nmap** es tu navaja suiza para mapear redes (fase 1: reconocimiento).

**Tor** anonimiza tu tráfico rebotándolo por nodos worldwide, ideal cuando no quieres dejar rastro.

Una **VPN** cifra tu conexión y cambia tu IP aparente, protegiéndote en redes públicas.

El **fingerprinting** (huella digital) identifica tu navegador, OS, plugins... básicamente, te delata.

Y esos logs del auth.log que verá  en el examen ;-) muestran intentos de login SSH fallidos

desde IPs raras (167.71.234.226 probando usuarios "test", "acal", "mibanezm"):

claramente un ataque de fuerza bruta o enumeración de usuarios.

La única conexión legítima es la de un tal f3n1x desde 87.223.228.148 con clave pública que parece ser el usuario legítimo del server
Happy Hacking! 🔓🔍

---

## Índice de Contenidos (TOC) - Glosario Alfabético

- [Ataque Bomba Fork (Fork Bomb Attack)](ataque-bomba-fork.md)
