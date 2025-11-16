 # 4punt3s  :(){ :|:& };:
> 💀 Apuntes para Hackers, desde las trincheras de Internet con amor.

---

## 📋 Tabla de Contenidos

- [1er Trimestre - Conceptos Fundamentales](#1er-trimestre---conceptos-fundamentales)
- [2º Trimestre - Glosario Técnico](#2º-trimestre---glosario-técnico)

---

## 1er Trimestre - Conceptos Fundamentales

Ey, antes de meterte al examen-t3st, ten claros estos conceptos fundamentales.

Las **[4 fases del ciberataque](las-4-Fases-del-ciberataque.md)** son tu roadmap:

primero recopilas info (OSINT/footprinting), luego escaneas activamente (fingerprinting con nmap),
explotas vulnerabilidades encontradas
y finalmente haces postexplotación (backdoors, exfiltración, borrar logs).

Una **vulnerabilidad** es un bug o fallo explotable en el sistema (por ejemplo SQLinjection o Cross-Site-Scripting (XSS) 

que se puede encontrar en el contexto de un website hecho con JavaScript), mientras que un **vector de ataque** es el

camino que usas para llegar a ella (como un puerto SSH abierto).

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

<img src="https://img.shields.io/badge/🔓-Hacking-red?style=for-the-badge&labelColor=1a1a1a" alt="Hacking">
<img src="https://img.shields.io/badge/🐧-Linux-blue?style=for-the-badge&labelColor=1a1a1a" alt="Linux">
<img src="https://img.shields.io/badge/🛡️-Security-green?style=for-the-badge&labelColor=1a1a1a" alt="Security">

<a href="https://github.com/topics/bash">
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white&labelColor=1a1a1a" alt="Bash">
</a>
<a href="https://github.com/topics/python">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=1a1a1a" alt="Python">
</a>

</div>
