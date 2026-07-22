# CyberLab - Red Team vs Blue Team

## Objetivo

Diseñar, construir, operar y documentar un Cyber Defense Lab con estándares profesionales simulando el trabajo de un Detection Engineer y un Blue Team Engineer.

## Tecnologías

- VMware Workstation
- Kali Linux
- Snort 2.9
- Suricata 8
- Zeek (próximamente)
- Wazuh (próximamente)
- Wireshark
- Npcap

## Topología

Host Windows

└── VMware VMnet3 (192.168.20.0/24)

- Kali Linux
- Metasploitable2
- OWASP Juice Shop
- DVWA
- Windows
- Otras máquinas vulnerables

Snort y Suricata se ejecutan en el host Windows monitoreando el adaptador VMnet3.

## Estado del proyecto

La Fase 1 dejó documentada la infraestructura y la primera detección ICMP. Los artefactos canónicos están versionados en `configs/`, `rules/`, `evidence/` y `docs/`.

- [x] Crear la red VMnet3
- [x] Instalar Npcap y Wireshark
- [x] Instalar y configurar Snort
- [x] Instalar y configurar Suricata
- [x] Crear la regla ICMP
- [x] Detectar ICMP con ambos sensores
- [ ] Revalidar Snort con la regla actualmente activa y archivar el PCAP
- [ ] Sprint 2.2: detección ARP
- [ ] Integrar Zeek
- [ ] Integrar Wazuh/SIEM

## Convenciones

- Toda configuración se documenta.
- Cada cambio se valida antes de continuar.
- Cada regla personalizada se almacena en `rules/`.
- Cada ataque exitoso tendrá una captura PCAP y evidencia.

## Licencia

Uso educativo y de investigación.
