hugo
====


What is does this role do?
--------------------------

This role installs hugo as well as a cron job that manages the site that is installed.


Meta
----

Files Managed:
  * /etc/iptables.d/hugo.rules
  * /etc/nginx/locations.d/[HUGO_SITE_URL]/
  * /etc/nginx/sites-available/[HUGO_SITE_NAME].conf
  * /etc/nginx/sites-enabled/[HUGO_SITE_NAME].conf
  * /etc/cron.d/[HUGO_SITE_NAME]
  * /usr/local/sbin/hugo-build-[HUGO_SITE_NAME]

Variables Required:
  hugo_sites:
  - site_name: the name for the site, should not have spaces
    site_path: where to serve the site from
    site_url: the url of the site
    source_url: a git repo containing the site
    source_host: the host of the git repository
    source_port: the port to connect to on the host containing the jekyll source material
    ssl_certificate_path: if using ssl, this must be the path to the certificate's full chain
    ssl_key_path: if using ssl, this must be the path to the certificate keyfile
    use_ssl: whether to use ssl
    webserver: which webserver role to use (nginx)


Files Required:
  * None

Optional Files:
  * None

Conflicting Roles:
  * None

Depends On:
  * [network](https://github.com/void-ansible-roles/network)
  * [nginx](https://github.com/void-ansible-roles/nginx)
