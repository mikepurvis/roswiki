Checkout the *master* branch of this repo at `(/var/www/wiki.ros.org/)data/plugin`.

Checkout the *conf* branch of this repo at `(/var/www/wiki.ros.org/)conf`.

**Apache configuration:**

*Alias for custom resources:*

    Alias /moin_static197/rostheme/ "/var/www/wiki.ros.org/data/plugin/custom/rostheme/"
    Alias /custom/ "/var/www/wiki.ros.org/data/plugin/custom/"

*Alias for moin resources:*

    Alias /moin_static197/ "/var/www/wiki.ros.org/venv/lib/python2.6/site-packages/MoinMoin/web/static/htdocs/"

*Register wsgi:*

    WSGIScriptAlias / /var/www/wiki.ros.org/conf/moin.wsgi
    WSGIDaemonProcess wgmoin user=apache group=apache home=/var/www/wiki.ros.org/data/ processes=50 threads=1 maximum-requests=1000 umask=0007 python-path=/var/www/wiki.ros.org/venv/lib/python2.6/site-packages/
    WSGIProcessGroup wgmoin

**Setup a cron job to dump the Wiki content:**

The script as well as the cron configuration can be found on the "wiki_dump_script" branch in this repo.
