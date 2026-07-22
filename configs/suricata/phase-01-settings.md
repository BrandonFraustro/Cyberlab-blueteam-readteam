# Suricata — parámetros validados de Fase 1

Fuente: C:/Program Files/Suricata/suricata.yaml, revisado el 22 de julio de 2026.

    HOME_NET: "[192.168.20.0/24]"
    EXTERNAL_NET: "!$HOME_NET"
    default-log-dir: C:/cyberlab/logs/suricata
    default-rule-path: C:/Program Files/Suricata/rules/
    rule-files:
      - local.rules

La regla canónica está en rules/suricata/icmp.rules.

