# Ansible Role: exploitdog net scanner

## Переменные

Все переменные, которые можно переопределить, хранятся в файле [defaults/main.yml](defaults/main.yml) и перечислены в таблице ниже.

| Name                                 | Default Value            | Description                                                                                   |
|--------------------------------------|--------------------------|-----------------------------------------------------------------------------------------------|
| `exploitdog_net_scanner_url`         | "https://exploitdog.com" | URL-адрес (обязательный параметр)                                                             |
| `exploitdog_sa_client_id`            | ""                       | ID сервис аккаунта (обязательный параметр)                                                    |
| `exploitdog_sa_client_secret`        | ""                       | Секретный ключ сервис аккаунта (обязательный параметр)                                        |
| `exploitdog_net_scanner_secrets`     | []                       | Секреты приложения                                                                            |
| `vm_network_interfaces`              | []                       | Сетевые интерфейсы для сканирования                                                           |
| `exploitdog_net_scanner_allowed_ips` | []                       | Разрешенные IP-подсети для сканирования                                                       |
| `vm_dns_servers`                     | []                       | DNS-серверы для разрешения доменов                                                            |
| `exploitdog_net_scanner_log_level`   | "info"                   | Уровень журнала: "debug", "info", "warning", "error"                                          |
| `exploitdog_net_scanner_version`     | "0.0.1-rc.3"             | Версия приложения (обязательный параметр, если не указан `exploitdog_net_scanner_build_id`)   |
| `exploitdog_net_scanner_build_id`    | ""                       | ID сборки приложения (обязательный параметр, если не указан `exploitdog_net_scanner_version`) |

## Пример ansible-playbook
```
- hosts: example
  roles:
    - ansible-net-scanner
  vars:
    exploitdog_net_scanner_url: https://exploitdog.com
    vm_network_interfaces:
      - "enp3s0"
      - "lo"
    exploitdog_net_scanner_allowed_ips:
      - "192.168.0.1/24"
      - "10.10.1.123/32"
      - "10.10.2.1/24"
    vm_dns_servers:
      - "8.8.8.8"
      - "1.1.1.1"
    exploitdog_net_scanner_log_level: "info"
    exploitdog_sa_client_id: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    exploitdog_sa_client_secret: "e8g_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    exploitdog_net_scanner_secrets:
      USER: "example"
      PASSWORD: "example"
      AGENT_TOKEN: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
      PRIVATE_KEY: |
        -----BEGIN RSA PRIVATE KEY-----
        MIICXQIBAAKBgQCRsG/tvMYCINsaXjM65AN3uYqMobf7QdeAnQSifK7SBVw4AZGV
        0OXpKyOwI8wJo6Cv+zRmsxZNeSRAlNXG1JUuch/heXAiawxHtv1frH5IwN+PNUJZ
        q24gTIQtriFZSFnP2j6Fn6OlFCEiQUJpaKcJQ7t+dZ8NJMP2mWvTc2axpQIDAQAB
        AoGATHiwR7muta9JUq3fdin5J/7cGrVIPTpyQ7AnnqKToOnvXfZ01I6yH5HlSa+A
        ig65aaYR+1ZFfqT3wm5dR+CN7Oh6eMMBvVd+rtIuilAeskup6A5iW5HTB/surD8R
        TT5HKfimnWxDxfZiv8pVWfAoCdE7sUy1g0QUOVhMoE9FiAECQQDC9tuoyMf8uxUQ
        jk9eAX3EnnNdKWiFkyTlY6D2/ztdu9kh/U4pkArHkcElAknEvqJOrrxN98wHeHVn
        u0PAUTx1AkEAv0x/C/3LmPlHAS9EtQ7+G7eONV7hhMOwwmd1wHBfhuxAEW8DaAR2
        3BfoCcGjxEez7SZ1aVRDTi1HtZMWR2a6cQJBAIkKX+hKCVi6X9odTehz/+VewxRu
        8MtDXKHo39H+IcqHKd7cYD6SwyD4cN0EuLmUjh3kcPQVA9MUduINHVhnQakCQDgG
        tWbTq99fkpYcO+kzPOTtO28SHMZ/cbNeDbSQtMmVQ6ZXdw3t0MnhDopc9hO0VFPu
        YZC5pwSsakYZj/rVcWECQQC6f4rd1jhS7wxNqZ7O/I+uwMmraq/BovKyL1zidN8K
        AlkAiHg6FJb1WvRy44caOvlPAuP+/YQIr8/SKkZDu6tU
        -----END RSA PRIVATE KEY-----
```
