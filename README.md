Ansible Role NGINX
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should
be mentioned here. For instance, if the role uses the EC2 module, it may be a
good idea to mention in this section that the boto package is required.

Role Variables
--------------

defaults file for ansible-role-nginx

```
#install
nginx_default_release: ""
nginx_ppa_use: true
nginx_ppa_version: stable
nginx_ppa_source: "nginx"
nginx_package_name: "nginx"

nginx_remove_default: false

# nginx custom configuration
nginx_replace_nginxconf: true
nginx_conf_path: "nginx.conf.j2"
nginx_templates_path: "{{ role_path }}/templates"

# nginx.conf
# nginx.conf:http
nginx_client_max_body_size: "64m"

# nginx.conf:extra
nginx_extra_conf_options: ""
# Example extra main options, used within the main nginx's context:
#   nginx_extra_conf_options: |
#     env VARIABLE;
#     include /etc/nginx/main.d/*.conf;

nginx_extra_http_options: ""
# Example extra http options, printed inside the main server http config:
#    nginx_extra_http_options: |
#      proxy_buffering    off;
#      proxy_set_header   X-Real-IP $remote_addr;
#      proxy_set_header   X-Scheme $scheme;
#      proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
#      proxy_set_header   Host $http_host;

# htpasswd
nginx_htpasswd: []
# - user: demo
#   password: demo

# dhparams
nginx_dhparam: false
#nginx_dhparam_file: /etc/nginx/dhparams.pem (optional)
#nginx_dhparam_size: 4096 (optional)
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in
regards to parameters that may need to be set for other roles, or variables that
are used from other roles.

Example Playbook
----------------

    - hosts: web
      roles:
         - nginx

License
-------

BSD

Author Information
------------------

Konstantin Deepezh, https://t.me/deusops
