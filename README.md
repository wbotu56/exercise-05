[![ansible-lint](https://github.com/wbotu56/exercise-05/actions/workflows/ansible-lint.yml/badge.svg?branch=uv)](https://github.com/wbotu56/exercise-05/actions/workflows/ansible-lint.yml)

# exercise-05

## Задание

1. [x] Установить Ansible
2. [x] Создать репозиторий `exercise-05`
3. [x] В ветке `dev` создать структуру из <https://github.com/express42/ansible-repertory>
4. [x] Создать плейбук `postgres.yaml` для установки postgres-server версии 14 (с ролью или в рамках плейбука, или используя внешнюю роль)
5. [x] Установка с помощью Ansible должна выполняться на хост, развернутый Vagrant’ом в занятии по Linux
6. [x] Vagrantfile должен находиться в корне репозитория

## DOD

1. [x] структура Ansible, в соответствии с <https://github.com/express42/ansible-repertory/tree/master#directory-structure>
2. [x] в корне репозитория `Readme.md` с описанием запуска плейбука
3. [x] Vagrantfile с параметрами, позволяющими установить postgres запуском плейбука (ip, пакеты)
    1. [x] На виртуальной машине установлена Ubuntu 22.04 или 24.04
    2. [x] ВМ имеет статический ip адрес.
    3. [x] Для ВМ настроена сеть, есть доступ в интернет.
    4. [x] ВМ доступна по ssh.
4. [x] Сервис postgres доступен снаружи на порту 5432
5. [x] После рестарта ВМ сервис работает

- [x] Создать репозиторий `exercise-05`
- [x] Положить vagrantfile и Ansible структуру в ветку `dev`.

## Запуск

1. Создать виртуальное окружение
    - Установить uv

    ```bash
    curl -LsSf https://astral.sh/uv/install.sh | sh
    ```

    - Создать виртуальное окружение при помощи uv

        ```bash
        uv sync
        ```

    - Активировать созданное виртуальное окружение

        ```bash
        source .venv/bin/activate
        ```

2. Развернуть виртуальную машину, описанную в Vagrantfile:

    ```bash
    vagrant up
    ```

3. Установить необходимые роли:

    ```bash
    ansible-galaxy install -r requirements.yml -p roles/vendor
    ```

4. Запустить плейбук, когда виртуальная машина будет доступна:

    ```bash
    ansible-playbook site.yml
    ```
