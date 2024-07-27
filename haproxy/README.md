
### `roles/haproxy/README.md`

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
| `haproxy_frontend_name`           | `main_frontend`                   | Имя фронтенда                                             |
| `haproxy_frontend_bind_address`   | `0.0.0.0`                         | Адрес для привязки фронтенда                              |
| `haproxy_frontend_port`           | `80`                              | Порт для привязки фронтенда                               |
| `haproxy_backend_name`            | `main_backend`                    | Имя бэкенда                                               |
| `haproxy_backend_servers`         | `['server1 192.168.1.10:80']`     | Список бэкенд серверов                                    |
| `haproxy_stats_enabled`           | `true`                            | Включить или отключить статистику HAProxy                 |
| `haproxy_stats_uri`               | `/haproxy?stats`                  | URI для доступа к статистике                              |
| `haproxy_stats_auth`              | `admin:admin`                     | Данные для авторизации доступа к статистике               |

## Пример использования

```yaml
- hosts: haproxy
  roles:
    - haproxy
