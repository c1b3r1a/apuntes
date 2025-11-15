# Fork Bomb Attack

## ¿Qué es una Fork Bomb?

Una **fork bomb** es un ataque de denegación de servicio (DoS) que explota la llamada del sistema `fork()` para crear procesos de forma recursiva e infinita, agotando los recursos del sistema (CPU, memoria, tabla de procesos) hasta provocar un cuelgue o bloqueo total.

## Ejemplo Clásico en Bash

```bash
:(){ :|:& };:
```

### Desglose del código:

- `:()` → Define una función llamada `:` (dos puntos)
- `{ :|:& }` → Cuerpo de la función: llama a sí misma dos veces (`:|:`) y ejecuta en background (`&`)
- `;` → Separador de comandos
- `:` → Ejecuta la función por primera vez

**Resultado**: Cada proceso crea dos procesos hijos, que a su vez crean dos más cada uno, en progresión exponencial (2, 4, 8, 16, 32, 64, 128...) hasta saturar el sistema.

## Variantes

### Python
```python
import os
while True:
    os.fork()
```

### C
```c
#include <unistd.h>
int main() {
    while(1) fork();
    return 0;
}
```

## Impacto y Consecuencias

- ✅ Saturación de la tabla de procesos (limite alcanzado)
- ✅ Consumo total de CPU
- ✅ Sistema inoperativo/congelado
- ✅ Imposibilidad de login o ejecución de comandos
- ⚠️ Puede requerir reinicio forzado del sistema

## Contramedidas y Mitigación

### 1. Límites de Procesos por Usuario (`ulimit`)

```bash
# Ver límites actuales
ulimit -a

# Limitar número de procesos a 500
ulimit -u 500

# Hacer permanente en /etc/security/limits.conf
echo "* hard nproc 500" >> /etc/security/limits.conf
echo "* soft nproc 500" >> /etc/security/limits.conf
```

### 2. Configuración en `/etc/security/limits.conf`

```
# Límites por usuario
usuario    hard    nproc    200
usuario    soft    nproc    150

# Límites globales
*          hard    nproc    1000
*          soft    nproc    800
```

### 3. Cgroups (Control Groups)

```bash
# Limitar procesos mediante cgroups
cgcreate -g cpu,memory:/limited
cgset -r pids.max=100 limited
cgexec -g cpu,memory:limited comando
```

### 4. Detección y Recuperación

```bash
# Desde otra sesión o terminal (si es posible)
pkill -u usuario_atacante

# Reiniciar servicios esenciales
systemctl restart systemd-logind

# Matar procesos por patrón
killall -9 nombre_proceso
```

## Contexto de Uso Ético

**Autorizado**:
- ✅ Laboratorios de prueba aislados (VMs, contenedores)
- ✅ Demostraciones educativas controladas
- ✅ Testing de límites de sistema antes de producción

**Prohibido**:
- ❌ Sistemas en producción
- ❌ Servidores compartidos sin autorización
- ❌ Infraestructura de terceros

## Práctica de Laboratorio Sugerida

### Escenario Controlado (Docker)

```dockerfile
FROM debian:latest
RUN useradd -m testuser
RUN echo "testuser hard nproc 50" >> /etc/security/limits.conf
USER testuser
WORKDIR /home/testuser
```

### Ejercicio

1. Lanzar contenedor con límites configurados
2. Intentar fork bomb
3. Observar cómo los límites previenen el colapso
4. Documentar comportamiento del sistema

## Referencias

- [Documentación ulimit](https://ss64.com/bash/ulimit.html)
- [Linux PAM limits](https://linux.die.net/man/5/limits.conf)
- [Cgroups Documentation](https://www.kernel.org/doc/Documentation/cgroup-v1/cgroups.txt)
- [OWASP - DoS Attacks](https://owasp.org/www-community/attacks/Denial_of_Service)
- [How to create a fork bomb in a Linux based system, and crash it](https://www.cyberciti.biz/faq/understanding-bash-fork-bomb/)

---

## Notas Importantes

**⚠️ Advertencia Legal y Ética**

Este documento tiene **exclusivamente fines educativos** en el contexto de formación en ciberseguridad. La ejecución de una fork bomb fuera de entornos controlados puede:

- Causar denegación de servicio y pérdida de disponibilidad del sistema
- Afectar a otros usuarios en sistemas multiusuario
- Provocar pérdida de datos no guardados
- Violar políticas de uso de sistemas corporativos o académicos
- Constituir un delito informático según el Código Penal (art. 264.2)

**Uso Autorizado Únicamente**:
- Máquinas virtuales personales
- Contenedores Docker aislados
- Laboratorios de prueba sin datos críticos
- Con supervisión del profesor en entorno académico

**NUNCA ejecutar en**:
- Servidores en producción
- Sistemas compartidos (sin autorización expresa)
- Equipos que no sean de tu propiedad
- Infraestructuras críticas o de terceros

**Responsabilidad**: El conocimiento de técnicas de ataque debe usarse exclusivamente para fortalecer defensas, nunca para causar daño. Como profesionales de ciberseguridad, nuestro código ético exige actuar siempre dentro de la legalidad y con autorización explícita.

---

**Principio de Defensa**: Conocer el ataque para implementar las protecciones adecuadas. Todo sistema Unix/Linux en producción debe tener límites de procesos configurados.
