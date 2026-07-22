# Troubleshooting — Fase 1

| Problema | Causa | Resolución |
|---|---|---|
| !HOME_NET no se analizaba | Variable o sintaxis incorrecta | Usar HOME_NET 192.168.20.0/24 y EXTERNAL_NET !$HOME_NET. |
| Regla ICMP inválida | Sintaxis incompatible o mal formada | Reducir la regla a ICMP, mensaje, SID y revisión. |
| Suricata no escribía logs | Program Files está protegido | Usar C:/cyberlab/logs/suricata. |
| Reglas inexistentes | Referencias a archivos no instalados | Usar local.rules explícitamente. |
| Captura fallida | Interfaz equivocada | Usar el dispositivo NPF de VMnet3 del runbook. |
| Aviso de threshold.config | Suricata no encuentra el archivo configurado | No bloquea la carga. Documentar o crear el archivo antes de introducir umbrales en fases posteriores. |
