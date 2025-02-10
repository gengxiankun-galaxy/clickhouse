CLICKHOUSE
=========

通过 ansible 部署在容器下运行的 ClickHouse 服务。

Installation
------------

`ansible-galaxy install gengxiankun.clickhouse`

Role Variables
--------------

variable | description
------------ | -------------
OPT_PATH | 部署目录
CLICKHOUSE_CONTAINER_NAME | ClickHouse 容器名称
CLICKHOUSE_IMAGE | ClickHouse Docker 镜像名称
CLICKHOUSE_NETWORK | docker network name ，其他依赖 ClickHouse 的服务，可通过绑定此网络实现与 ClickHouse 的通信（同样容器服务的情况下）
CLICKHOUSE_PORT | ClickHouse 服务对外提供服务的端口
CLICKHOUSE_HTTP_PORT | ClickHouse 服务对外提供 HTTP 服务的端口
CLICKHOUSE_NOFILE_SOFT | 可打开的文件描述符的最大数（超过会警告）
CLICKHOUSE_NOFILE_HARD | 可打开的文件描述符的最大数（超过会报错）


Dependencies
------------

- Docker

Example Playbook
----------------

    - hosts: servers
      roles:
        - gengxiankun.clickhouse
      vars:
        - OPT_PATH: /opt
        - CLICKHOUSE_CONTAINER_NAME: clickhouse
        - CLICKHOUSE_IMAGE: clickhouse
        - CLICKHOUSE_NETWORK: clickhouse
        - CLICKHOUSE_NOFILE_SOFT: 262144
        - CLICKHOUSE_NOFILE_HARD: 262144
        - CLICKHOUSE_PORT: 8123
        - CLICKHOUSE_HTTP_PORT: 9000

License
-------

BSD

Author Information
------------------

This role was created in 2021 by Xiankun Geng, Learn more about the author's role in [galaxy](https://galaxy.ansible.com/gengxiankun).
