# 4punt3s  :(){ :|:& };:
> 💀 Apuntes para Hackers, desde las trincheras de Internet con amor.

<div align="center">

![Hacking](https://img.shields.io/badge/🔓-Hacking-red?style=for-the-badge&labelColor=1a1a1a)
![Linux](https://img.shields.io/badge/🐧-Linux-blue?style=for-the-badge&labelColor=1a1a1a)
![Security](https://img.shields.io/badge/🛡️-Security-green?style=for-the-badge&labelColor=1a1a1a)

</div>

---

## 📋 Tabla de Contenidos

- [1er Trimestre - Conceptos Fundamentales](#1er-trimestre---conceptos-fundamentales)
- [2º Trimestre - Glosario Técnico](#2º-trimestre---glosario-técnico)

---

## 1er Trimestre - Conceptos Fundamentales

Ey, antes de meterte al examen-t3st, ten claros estos conceptos fundamentales.

Las **4 fases del ciberataque** son tu roadmap:

primero recopilas info (OSINT/footprinting), luego escaneas activamente (fingerprinting con nmap),
explotas vulnerabilidades encontradas
y finalmente haces postexplotación (backdoors, exfiltración, borrar logs).

### Vulnerabilidad vs Vector de Ataque

Una **[vulnerabilidad](https://es.wikipedia.org/wiki/Vulnerabilidad_inform%C3%A1tica)** es un fallo o debilidad explotable en un sistema, aplicación o servicio.

Ejemplos comunes:
- **[SQL Injection](https://es.wikipedia.org/wiki/Inyecci%C3%B3n_SQL)** (SQLi): inyección de código SQL malicioso en formularios web
- **[Cross-Site Scripting](https://es.wikipedia.org/wiki/Cross-site_scripting)** (XSS): inyección de scripts en páginas web que ejecutan código en el navegador de la víctima
- **[Buffer Overflow](https://es.wikipedia.org/wiki/Desbordamiento_de_buffer)**: desbordamiento de memoria que permite ejecutar código arbitrario
- **Contraseñas débiles**: credenciales fáciles de adivinar o crackear

Por otro lado, un **vector de ataque** es el método, camino o canal que utiliza el atacante para explotar esa vulnerabilidad.

Ejemplos de vectores:
- Puerto [SSH](https://es.wikipedia.org/wiki/Secure_Shell) (22) abierto → permite ataques de fuerza bruta contra contraseñas débiles
- Formulario de login web → punto de entrada para SQLi o credential stuffing
- Campo de comentarios sin sanitizar → vector para inyectar XSS
- Adjunto de email malicioso → vector para entregar malware/ransomware

**Relación**: La vulnerabilidad es la **debilidad**, el vector es la **ruta de acceso** a esa debilidad.

### Herramientas Esenciales

**[Geolocalización IP](https://es.wikipedia.org/wiki/Geolocalizaci%C3%B3n)** → Te dice dónde está físicamente un servidor (comandos: `curl ipinfo.io`, `geoiplookup`)

**[Sniffer](https://es.wikipedia.org/wiki/Analizador_de_paquetes)** → Como [Wireshark](https://es.wikipedia.org/wiki/Wireshark) "huele" paquetes de red en tiempo real, perfecto para ver qué viaja sin cifrar.

**[Nmap](https://es.wikipedia.org/wiki/Nmap)** → Tu navaja suiza para mapear redes (fase 1: reconocimiento).

**[Tor](https://es.wikipedia.org/wiki/Tor_(red_de_anonimato))** → Anonimiza tu tráfico rebotándolo por nodos worldwide, ideal cuando no quieres dejar rastro.

**[VPN](https://es.wikipedia.org/wiki/Red_privada_virtual)** → Cifra tu conexión y cambia tu IP aparente, protegiéndote en redes públicas.

**[Fingerprinting](https://en.wikipedia.org/wiki/Device_fingerprint)** → (huella digital) identifica tu navegador, OS, plugins... básicamente, te delata.

Y esos logs del auth.log que verá  en el examen ;-) muestran intentos de login SSH fallidos

desde IPs raras (167.71.234.226 probando usuarios "test", "acal", "mibanezm"):

claramente un ataque de fuerza bruta o enumeración de usuarios.

La única conexión legítima es la de un tal f3n1x desde 87.223.228.148 con clave pública que parece ser el usuario legítimo del server
Happy Hacking! 🔓🔍


## 2º Trimestre - Glosario Técnico

Lorem Ipsum Torvalds, nihil Sine RMS.
Dennis Ritchie dixit, ora et jakea.
ESR, says... la cathedral an bazaar.
Ava Lovelace, in Memoriam.
Grace Hopper magnificat.
Opus technotronic musica est.
Principia Discoridia - Eris guidam.

---

### 📚 Glosario Alfabético

| **Tema** | **Descripción** | **Categoría** |
|:---------|:----------------|:--------------|
| [🔥 Ataque Bomba Fork (Fork Bomb)](ataque-bomba-fork.md) | Ataque DoS mediante recursión infinita de procesos | DoS / Linux |

---

<div align="center">

<a href="https://github.com/topics/bash">
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white&labelColor=1a1a1a" alt="Bash">
</a>
<a href="https://github.com/topics/python">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=1a1a1a" alt="Python">
</a>

</div>
