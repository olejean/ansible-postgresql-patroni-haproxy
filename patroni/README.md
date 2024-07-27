
### Роль: patroni

**Название файла:** `roles/patroni/README.md`

```markdown
# Роль Ansible: Patroni

Эта роль устанавливает и настраивает Patroni для управления кластером PostgreSQL с высокой доступностью.

## Требования

- Ansible 2.9 или выше
- Ubuntu 20.04 или выше
- Установленный etcd

## Переменные роли

| Переменная               | Значение по умолчанию          | Описание                                              |
|--------------------------|--------------------------------|-------------------------------------------------------|
| `patroni_version`        | `2.0.1`                        | Версия Patroni для установки                          |
| `patroni_config_file`    | `/etc/patroni.yml`             | Путь до конфигурационного файла Patroni               |
| `postgresql_data_dir`    | `/var/lib/postgresql/12/main`  | Директория для хранения данных PostgreSQL             |
| `patroni_scope`          | `postgres-cluster`             | Имя кластера Patroni                                  |
| `etcd_cluster`           | `http://localhost:2379`        | Адрес кластера etcd для использования Patroni         |

## Зависимости

- Роль etcd

## Пример использования

```yaml
- hosts: patroni
  roles:
    - patroni
