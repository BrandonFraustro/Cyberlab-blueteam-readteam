# Changelog

## 2026-07-22 — Cierre documental de Fase 1

- Se versionaron reglas ICMP para Snort y Suricata.
- Se documentaron parámetros, runbook y troubleshooting.
- Se añadieron extractos curados de alertas de Suricata.
- Pendiente: revalidar Snort con la regla activa y archivar un PCAP de la prueba.

## 2026-07-22 — Cierre operacional de Fase 1

- Snort detectó cuatro solicitudes y cuatro respuestas ICMP con la firma CYBERLAB ICMP Ping.
- Suricata registró el mismo flujo en fast.log y eve.json.
- Se archivó pcaps/phase-01-icmp-validation.pcapng.
- La Fase 1 cumple los criterios de aceptación y queda cerrada.
