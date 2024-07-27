# Роль Ansible: Patroni и PostgreSQL

Эта роль устанавливает и настраивает как Patroni, так и PostgreSQL для обеспечения высокой доступности базы данных.

## Требования

- Ansible 2.9 или выше
- Ubuntu 20.04 или выше
- Установленный etcd

## Переменные роли

| Переменная                      | Значение по умолчанию           | Описание                                                   |
|---------------------------------|---------------------------------|------------------------------------------------------------|
| `patroni_version`               | `3.3.2`                         | Версия Patroni для установки                               |
| `postgresql_version`            | `16`                            | Версия PostgreSQL для установки                            |
| `patroni_config_file`           | `/etc/patroni.yml`              | Путь до конфигурационного файла Patroni                    |
| `postgresql_data_dir`           | `/var/lib/postgresql/12/main`   | Директория для хранения данных PostgreSQL                  |
| `patroni_scope`                 | `postgres-cluster`              | Имя кластера Patroni                                       |
| `etcd_cluster`                  | `http://localhost:2379`         | Адрес кластера etcd для использования Patroni              |
| `patroni_loop_wait`             | `10`                            | Количество секунд для ожидания в цикле Patroni             |
| `patroni_ttl`                   | `30`                            | Время жизни (TTL) для блокировки лидера                    |
| `patroni_retry_timeout`         | `10`                            | Таймаут для повторных попыток операций Patroni             |
| `postgresql_parameters`         | `{}`                            | Конфигурационные параметры (GUC) для PostgreSQL            |
| `patroni_pg_hba`                | `[]`                            | Список строк для генерации файла pg_hba.conf Patroni       |
| `patroni_pg_ident`              | `[]`                            | Список строк для генерации файла pg_ident.conf Patroni     |

## Зависимости

- Роль etcd

## Пример использования

```yaml
- hosts: patroni_postgresql
  roles:
    - patroni_postgresql
