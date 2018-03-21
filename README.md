Install Composer [![Build Status](https://travis-ci.org/shengyou/ansible-role-composer.svg?branch=master)](https://travis-ci.org/shengyou/ansible-role-composer)
=========

安裝 composer。

適用於
* Ubuntu 14.04
* Ubuntu 16.04
* CentOS 6
* CentOS 7

Requirements
------------

* ansible >= 2.4
* python >= 2.6
* php (cli) >= 5.6

Role Variables
--------------

要將 `.composer` 放於哪一個 user 的家目錄之下，預設為 `www-data`
* composer_user: (default: www-data)
* composer_user_home_path: (default: /var/www)

如果需要一併在 `.composer` 之下存放特定的 `auth.json` 及 `config.json`，請設置下述變數，變數內容為檔案於 client 的存放路徑。
* composer_auth_file_src:
* composer_config_file_src:


Dependencies
------------

none.

Example Playbook
----------------

```
- name: ansible-role-composer.yml
  hosts: your_host
  gather_facts: yes
  become: yes

  vars:
    composer_user: "www-data"
    composer_user_home_path: "/var/www"

    composer_auth_file_src: "path/to/your/composer/auth.json"
    composer_config_file_src: "path/to/your/composer/config.json"

  roles:
    - ansible-role-composer
```

License
-------

MIT
