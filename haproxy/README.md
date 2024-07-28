
# Роль Ansible: HAPROXY

```markdown
# Роль Ansible: HAProxy

Эта роль устанавливает и настраивает HAProxy для балансировки нагрузки и проксирования запросов к бекенд-серверам.

## Требования

- Ansible 2.9 или выше
- Ubuntu 20.04 или выше

## Переменные роли

| Переменная                        | Значение по умолчанию             | Описание                                                  |
|-----------------------------------|-----------------------------------|-----------------------------------------------------------|
| `haproxy_config_file`             | `/etc/haproxy/haproxy.cfg`        | Путь до конфигурационного файла HAProxy                   |
| `haproxy_frontend_name`           | `stats`                           | Имя фронтенда                                             |
| `haproxy_frontend_port`           | `8080`                            | Порт для привязки фронтенда                               |
| `haproxy_backend_name`            | `patroni`                         | Имя бэкенда                                               |
| `haproxy_backend_servers`         | `['patroni1 192.168.1.13:8008']`  | Список бэкенд серверов                                    |
| `haproxy_backend_servers`         | `['patroni2 192.168.1.14:8008']`  | Список бэкенд серверов                                    |
| `haproxy_backend_servers`         | `['patroni3 192.168.1.15:8008']`  | Список бэкенд серверов                                    | 
| `haproxy_stats_enabled`           | `true`                            | Включить или отключить статистику HAProxy                 |
| `haproxy_stats_uri`               | `/                                | URI для доступа к статистике                              |
| `haproxy_stats_auth`              | `admin:admin`                     | Данные для авторизации доступа к статистике               |

## Пример использования

```yaml
- hosts: haproxy
  roles:
    - haproxy
