# Snort — parámetros validados de Fase 1

Fuente: C:/Snort/etc/snort.conf, revisado el 22 de julio de 2026.

    ipvar HOME_NET 192.168.20.0/24
    ipvar EXTERNAL_NET !$HOME_NET
    var RULE_PATH ../rules
    config logdir: ../log
    include $RULE_PATH/local.rules

La regla canónica está en rules/snort/icmp.rules.

