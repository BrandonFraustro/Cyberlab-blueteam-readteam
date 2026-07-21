# Phase 01 - Infrastructure & IDS Deployment

**Proyecto:** CyberLab - Red Team vs Blue Team Lab

**Autor:** Brandon Fraustro

**Estado:** ✅ Finalizada

**Versión:** 1.0

---

# Objetivo

Diseñar e implementar la infraestructura base del laboratorio de ciberseguridad donde se desplegarán herramientas de detección, monitoreo, análisis forense y respuesta a incidentes.

Esta fase establece los cimientos técnicos del laboratorio para las siguientes fases del proyecto.

---

# Arquitectura

```
                   Windows Host

        +----------------------------------+
        |                                  |
        | Wireshark                        |
        |                                  |
        | Snort IDS                        |
        |                                  |
        | Suricata IDS                     |
        |                                  |
        +---------------+------------------+
                        |
               VMware VMnet3
              192.168.20.0/24
                        |
      +-----------------+------------------+
      |                                    |
   Kali Linux                     Máquina Vulnerable
```

---

# Objetivos de la fase

- Construir una red aislada para pruebas.
- Instalar Snort.
- Instalar Suricata.
- Configurar captura mediante Npcap.
- Crear las primeras reglas.
- Validar funcionamiento de ambos IDS.

---

# Componentes implementados

## Host

Windows

Responsabilidades:

- Monitoreo
- Captura
- IDS
- Almacenamiento de evidencias

---

## Red de laboratorio

VMware VMnet3

Subnet

192.168.20.0/24

---

## Sensores desplegados

### Snort

Versión

2.9.20

Funciones

- IDS
- Reglas personalizadas
- Captura mediante Npcap

---

### Suricata

Versión

8.0.6

Funciones

- IDS
- eve.json
- fast.log
- Captura mediante Npcap

---

# Problemas encontrados

## Problema 1

HOME_NET mal configurado.

### Solución

Configurar correctamente:

```

var HOME_NET 192.168.20.0/24

```

---

## Problema 2

Errores de sintaxis en local.rules

### Solución

Reescribir las reglas utilizando el formato correcto para Snort.

---

## Problema 3

Suricata no podía escribir logs.

### Causa

Windows protege Program Files.

### Solución

Mover el directorio de logs a

```

C:\CyberLab\logs\suricata

```

---

## Problema 4

Suricata no encontraba botcc.rules

### Solución

Eliminar referencias a reglas inexistentes.

---

## Problema 5

Selección incorrecta de interfaz.

### Solución

Utilizar directamente el dispositivo NPF.

```

\Device\NPF_{689F61F5-0C39-42D2-8E74-B86E15E9048E}

```

---

# Validaciones realizadas

## Snort

Configuración validada

```

snort -T

```

Resultado

Configuración válida.

---

## Suricata

Configuración validada

```

suricata -T

```

Resultado

Configuración válida.

---

# Primera detección

Regla implementada

ICMP Ping

Validación realizada desde Kali.

Resultado

Snort detectó correctamente el tráfico.

Suricata detectó correctamente el tráfico.

---

# Evidencias

## Snort

Consola

```

CYBERLAB ICMP Ping

```

---

## Suricata

fast.log

```

CYBERLAB ICMP Ping

```

---

eve.json

Evento registrado correctamente.

---

# Estructura de directorios

```
CyberLab/

docs/
reports/
phase-01/

detection/
snort/
suricata/

evidence/

scripts/

dashboards/

logs/

```

---

# Lecciones aprendidas

- Npcap es obligatorio para captura en Windows.
- Snort y Suricata pueden convivir sobre la misma red.
- Program Files no es una buena ubicación para los logs.
- Suricata produce información mucho más rica mediante eve.json.
- Es recomendable separar configuración, reglas y evidencias.

---

# Estado de la fase

| Componente      | Estado |
| --------------- | ------ |
| Infraestructura | ✅     |
| Snort           | ✅     |
| Suricata        | ✅     |
| Captura         | ✅     |
| Validación      | ✅     |
| Primera regla   | ✅     |

---

# Próxima fase

## Phase 02

Detection Engineering

Primer sprint

ARP

Objetivos

- Comprender ARP.
- Detectar ARP Scan.
- Detectar ARP Spoofing.
- Comparar Snort vs Suricata.
- Generar nuevas reglas.
- Documentar evidencias.
