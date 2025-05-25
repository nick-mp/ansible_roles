# Ansible Playbook для Clickhouse, Vector и LightHouse

Этот playbook устанавливает и настраивает стек для сбора и визуализации логов, состоящий из:
- Clickhouse - колоночной СУБД для хранения логов
- Vector - инструмента для сбора и обработки логов
- LightHouse - веб-интерфейса для просмотра логов

## Структура проекта

```
ansible_Clickhouse_vector_lighthouse/
├── clickhouse-role/     # Роль для установки и настройки Clickhouse
├── vector-role/         # Роль для установки и настройки Vector
├── lighthouse-role/     # Роль для установки и настройки LightHouse
├── inventory/           # Инвентарь хостов
├── requirements.yml     # Зависимости ролей
└── site.yml            # Основной playbook
```

## Требования

- Ansible 2.9 или выше
- CentOS/RHEL 7 или выше
- Доступ к интернету для загрузки пакетов

## Роли

### Clickhouse Role

Роль для установки и настройки Clickhouse - колоночной СУБД для аналитики.

Основные функции:
- Установка Clickhouse из официальных репозиториев
- Настройка сервиса
- Создание базы данных для логов

### Vector Role

Роль для установки и настройки Vector - инструмента для сбора и обработки логов.

Основные функции:
- Установка Vector из официальных репозиториев
- Настройка конфигурации для сбора логов
- Настройка сервиса

### LightHouse Role

Роль для установки и настройки LightHouse - веб-интерфейса для просмотра логов.

Основные функции:
- Установка и настройка nginx
- Загрузка и установка LightHouse
- Настройка веб-сервера

## Использование

1. Клонируйте репозиторий:
```bash
git clone https://github.com/nick-mp/ansible_roles.git
cd ansible_Clickhouse_vector_lighthouse
```

2. Установите зависимости:
```bash
ansible-galaxy install -r requirements.yml
```

3. Настройте инвентарь в директории `inventory/`

4. Запустите playbook:
```bash
ansible-playbook -i inventory/prod.yml site.yml
```

## Переменные

Основные переменные для каждой роли находятся в соответствующих директориях:
- `clickhouse-role/defaults/main.yml`
- `vector-role/defaults/main.yml`
- `lighthouse-role/defaults/main.yml`

## Лицензия

MIT

