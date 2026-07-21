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

## Roadmap

- [x] Crear la red VMnet3
- [x] Instalar Npcap
- [x] Instalar Wireshark
- [x] Instalar Snort
- [x] Instalar Suricata
- [ ] Configurar Snort
- [ ] Configurar Suricata
- [ ] Crear primeras reglas
- [ ] Detectar ICMP
- [ ] Detectar Nmap
- [ ] Integrar Zeek
- [ ] Integrar Wazuh
- [ ] Integrar SIEM

## Convenciones

- Toda configuración se documenta.
- Cada cambio se valida antes de continuar.
- Cada regla personalizada se almacena en `rules/`.
- Cada ataque exitoso tendrá una captura PCAP y evidencia.

## Licencia

Uso educativo y de investigación.
