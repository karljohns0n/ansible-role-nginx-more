# Ansible Role: nginx-more

This role installs nginx-more for CentOS / RedHat. Nginx-more is a build of Nginx with additional modules such as HTTP2, PageSpeed, Brotli, More Headers, Cache Purge, VTS, GeoIP2. It's compiled using recent GCC version and latest OpenSSL sources. It also includes some built-in configurations such as WordPress and Laravel php-fpm setup. More information can be found on this package [here](https://github.com/karljohns0n/nginx-more).

## Requirements

This role was developed using Ansible 2.7. Backwards compatibility is not guaranteed.

## Role Variables

Nginx-more already provides a lot of built-in configurations therefore no templates are currently included in the playbook.

### SELinux

Fresh installation of nginx-more may conflict with SELinux. A role variable `nginx_selinux_permissive` is defined (boolean, default: 'true') to temporarily disable SELinux restrictions for the httpd_t context if set to `true` and if Ansible detect that SELinux is in enforcing mode. Those tasks are skipped if SELinux is disabled.

## Dependencies

Clean OS installation without a Web server (apache, nginx, etc..) installed. The playbook will detect a conflict if nginx is installed.

## Example Playbook

    - hosts: servers
      roles:
         - { role: aeris.nginx-more }

## License

MIT

## Author Information

Karl Johnson
