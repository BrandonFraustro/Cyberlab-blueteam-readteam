# Runbook — Validación reproducible de Fase 1

## Propósito

Verificar que Snort y Suricata observan VMnet3 (192.168.20.0/24) y generan CYBERLAB ICMP Ping.

## Prerrequisitos

- Npcap instalado.
- Kali: 192.168.20.129; objetivo: 192.168.20.128.
- Las reglas en rules/snort/icmp.rules y rules/suricata/icmp.rules están desplegadas sin comentar.

## Preparación

1. Copiar la regla Snort a C:/Snort/rules/local.rules.
2. Copiar la regla Suricata a C:/Program Files/Suricata/rules/local.rules.
3. Confirmar los parámetros de configuración en configs/.

## Validación

    cd C:/Snort/bin
    ./snort.exe -T -i 7 -c C:/Snort/etc/snort.conf
    ./snort.exe -i 7 -A console -c C:/Snort/etc/snort.conf

    cd C:/Program Files/Suricata
    ./suricata.exe -T -c ./suricata.yaml
    ./suricata.exe -c ./suricata.yaml -i \\Device\\NPF_{689F61F5-0C39-42D2-8E74-B86E15E9048E}

Desde Kali:

    ping -c 4 192.168.20.128

## Criterios de aceptación

- Las pruebas de configuración terminan correctamente.
- Snort muestra CYBERLAB ICMP Ping.
- Suricata registra la firma en fast.log y un evento alert en eve.json.
- Se guardan extractos en evidence/ y un PCAP seleccionado en pcaps/.

